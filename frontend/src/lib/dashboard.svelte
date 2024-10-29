<script lang="ts">
    export let userData: any;

    let username = userData.user.username;
    let password = userData.user.password_original;
    let encrypted = userData.user.password_encrypted;
    let salt = userData.user.salt_value;
    let hash = userData.user.hash_value;
    let final = userData.user.final_password;
</script>

<body>
    <div class="con">
        <div class="usd">
            <h1 class="">Welcome, {username}</h1>
        </div>

        <form method="POST" action="?/logout">
            <button>Logout</button>
        </form>

        <div class="card">
            <label for="l">Password</label>
            <div class="textbox">{ password ? password : "Not set" }</div>
            <label for="l">Password Encrypt</label>
            <div class="textbox">{ encrypted ? encrypted : "Not set" }</div>
            <label for="l">Salt Value</label>
            <div class="textbox">{ salt ? salt : "Not set" }</div>
            <label for="l">Hash Values</label>
            <div class="textbox">{ hash ? hash : "Not set" }</div>
            <label for="l">Final Password</label>
            <div class="textbox">{ final ? final : "Not set" }</div>
        </div>

        <!-- <div class="tree"> -->
        <!--     <ul> -->
        <!--         <li> -->
        <!--             <a href="#">Password</a> -->
        <!--             <ul> -->
        <!--                 <li> -->
        <!--                     <ul> -->
        <!--                         <li> -->
        <!--                             <a href="#">Password_Encrypt</a> -->
        <!--                         </li> -->
        <!--                     </ul> -->
        <!--                 </li> -->
        <!--                 <li> -->
        <!--                     <ul> -->
        <!--                         <ul> -->
        <!--                         <li><a href="#">Salt_Value</a></li> -->
        <!--                         <li> -->
        <!--                             <a href="#">Hash_Value</a> -->
        <!--                             <ul> -->
        <!--                                 <li><a href="#">Hash_Salting</a> -->
        <!--                                     <ul> -->
        <!--                                         <li><a href="#">Final_Password</a> -->
        <!--                                         </li> -->
        <!--                                     </ul> -->
        <!--                                 </li> -->
        <!--                             </ul> -->
        <!--                         </li> -->
        <!--                     </ul> -->
        <!--                 </li> -->
        <!--             </ul> -->
        <!--         </li> -->
        <!--     </ul> -->
        <!-- </div> -->
    </div>

    
</body>

<style>
    body{
        background: linear-gradient(to bottom, #0f0c29, #302b63, #24243e);
    }

    form {
        padding: 10px;
    }

    button{
        width: 160px;
        height: 40px;
        margin: 1px auto;
        justify-content: center;
        display: block;
        color: #fff;
        background: #573b8a;
        font-size: 1em;
        font-weight: bold;
        margin-top: 15px;
        outline: none;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }

    .card{
        z-index: 2;
        display: flex;
        flex-flow: column nowrap;
        justify-content: center;
        padding: 1% 5%;
        box-sizing: border-box;
        font-weight: bold;
        font-family: 'Jost', sans-serif;
    }

    .card div{
        font-size: 1.2em;
    }
    
    .textbox{
        background-color: #eee;
        padding: 12px;
        margin: 7px;
        color: #573b8a;
        font-size: 1.3em;
        font-weight: bold;
        font-family: 'Jost', sans-serif;
        /* width: 635px; */
        border-radius: 10px;
        overflow: scroll;
    }
    label{
        color: #fff;
        padding-left: 2%;
    }

    .con{
        width: auto;
        height: 775px;
        overflow: hidden;
        box-shadow: 5px 20px 50px #000;
        background: url("https://doc-08-2c-docs.googleusercontent.com/docs/securesc/68c90smiglihng9534mvqmq1946dmis5/fo0picsp1nhiucmc0l25s29respgpr4j/1631524275000/03522360960922298374/03522360960922298374/1Sx0jhdpEpnNIydS4rnN4kHSJtU1EyWka?e=view&authuser=0&nonce=gcrocepgbb17m&user=03522360960922298374&hash=tfhgbs86ka6divo3llbvp93mg4csvb38") no-repeat center/ cover;
        margin-top: 5%;
        margin-bottom: 5%;
        margin-left: 5%;
        margin-right: 5%;
        border-radius: 10px;
    }
    .usd{
        display: flex;
        padding: 50px;
        justify-content: center;
        height: 20%;
        background-color: #eee;
        border-radius: 10px 10px 60% 60%;
        font-family: 'Jost', sans-serif;
    }
    .usd h1{
        color: #573b8a;
        font-size: 2.3em;
        font-weight: bold;
    }
    
    * {margin: 0; padding: 0;}

    .tree{
        display: flex;
        justify-content: right;
        padding-top: 2%;
        padding-right: 4%;
        
    }

    .tree ul {
        padding-top: 20px; position: relative;
        
        transition: all 0.5s;
        -webkit-transition: all 0.5s;
        -moz-transition: all 0.5s;
    }

    .tree li {
        float: left; text-align: center;
        list-style-type: none;
        position: relative;
        padding: 20px 5px 0 5px;
        
        transition: all 0.5s;
        -webkit-transition: all 0.5s;
        -moz-transition: all 0.5s;
    }

    /*We will use ::before and ::after to draw the connectors*/

    .tree li::before, .tree li::after{
        content: '';
        position: absolute; top: 0; right: 50%;
        border-top: 1px solid #ccc;
        width: 50%; height: 20px;
    }
    .tree li::after{
        right: auto; left: 50%;
        border-left: 1px solid #ccc;
    }

    /*We need to remove left-right connectors from elements without 
    any siblings*/
    .tree li:only-child::after, .tree li:only-child::before {
        display: none;
    }

    /*Remove space from the top of single children*/
    .tree li:only-child{ padding-top: 0;}

    /*Remove left connector from first child and 
    right connector from last child*/
    .tree li:first-child::before, .tree li:last-child::after{
        border: 0 none;
    }
    /*Adding back the vertical connector to the last nodes*/
    .tree li:last-child::before{
        border-right: 1px solid #ccc;
        border-radius: 0 5px 0 0;
        -webkit-border-radius: 0 5px 0 0;
        -moz-border-radius: 0 5px 0 0;
    }
    .tree li:first-child::after{
        border-radius: 5px 0 0 0;
        -webkit-border-radius: 5px 0 0 0;
        -moz-border-radius: 5px 0 0 0;
    }

    /*Time to add downward connectors from parents*/
    .tree ul ul::before{
        content: '';
        position: absolute; top: 0; left: 50%;
        border-left: 1px solid #ccc;
        width: 0; height: 20px;
    }

    .tree li a{
        border: 1px solid #ccc;
        padding: 5px 10px;
        text-decoration: none;
        color: #666;
        font-family: 'Jost', sans-serif;
        font-size: 2.3em;
        display: inline-block;
        font: bold;
        

        
        border-radius: 5px;
        -webkit-border-radius: 5px;
        -moz-border-radius: 5px;
        
        transition: all 0.5s;
        -webkit-transition: all 0.5s;
        -moz-transition: all 0.5s;
    }

    /*Time for some hover effects*/
    /*We will apply the hover effect the the lineage of the element also*/
    .tree li a:hover, .tree li a:hover+ul li a {
        background: #eee; color: #573b8a; border: 1px solid #94a0b4;
    }
    /*Connector styles on hover*/
    .tree li a:hover+ul li::after, 
    .tree li a:hover+ul li::before,
    .tree li a:hover+ul::before, 
    .tree li a:hover+ul ul::before{
        border-color:  #94a0b4;
    }


</style>
