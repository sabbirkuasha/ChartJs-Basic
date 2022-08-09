<div id="main"> 
    <div id="header">
    </div>
    <div id="content2"> 
    </div>
    <div id="content"> 
    </div>
    
    <!-- <div id="header2">
    </div>
    <div id="content2"> 
    </div> -->
</div>

<div>
    
</div>

<style>
    #main{
    width:360px;
    height:500px;
    position:relative;
    }

    #header{
    position:absolute;
    left: 1%;
    height:50%;
    width:20%;
    background-color:orange;
    /* border: 2px solid red; */
    top:0;
    opacity:0.8;
    z-index:99999;
    }
    #content2{
    position:absolute;
    left: 1%;
    height:20%;
    width:20%;
    background-color:rgb(56, 3, 244);
    border:2px solid rgb(255, 0, 242);
    bottom:0;
    z-index:1;
    }
    #content{
    position:absolute;
    left: 1%;
    height:10%;
    width:20%;
    background-color:cyan;
    border:2px solid rgb(255, 0, 0);
    bottom:0;
    z-index:1;
    }
    
    /* #header2{
    position:absolute;
    left: 29%;
    height:60%;
    width:20%;
    background-color:orange;
    border: 2px solid red;
    top:0;
    opacity:0.8;
    z-index:99999;
    }
    #content2{
    position:absolute;
    left: 29%;
    height:70%;
    width:20%;
    background-color:cyan;
    border:1px solid blue;
    bottom:0;
    z-index:1;
    } */
</style>