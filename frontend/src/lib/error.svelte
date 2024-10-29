<script lang="ts">
    export let userData: any;
</script>

<div class="bg">
    <i class="fa-solid fa-triangle-exclamation fa-10x"></i>
    <h1>{userData.errors}</h1>
    <form method="POST" action="?/close">
        <button>Close</button>
    </form>
</div>

<style> 
    .bg{
        background-color: #eee;
        width: 350px;
        height: 500px;
        border-radius: 10px;
        font-family: 'Jost', sans-serif;
        justify-content: center;
        position: absolute;
        z-index: 2;
    }
    .bg h1{
        font-size: 1.1em;
        font-weight: bold;
        color: #573b8a;
        text-align: center;
        margin-top: 22%;
    }

    .bg i {
        color: #573b8a;
        justify-content: center;
        display: flex;
        margin-top: 15%;
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
        margin-top: 17%;
    }
</style>
