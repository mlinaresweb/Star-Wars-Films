<template>
    <hr>
    <footer>
        <p>&copy; Manel Linares, 2022</p>
    <div class="enlaces">
        <a href="https://www.linkedin.com/in/manellinares/">
        <i class="fa-brands fa-linkedin"></i>
        </a>
        <a href="https://github.com/mlinaresweb">
        <i class="fa-brands fa-github"></i>
        </a>
  </div>
  </footer>
</template>
    
<script setup>
</script>
    
<style scoped>

footer {
     bottom: 0;
     display: flex;
     flex-flow: row wrap;
     justify-content: space-between;
     margin: 10px 70px;
     align-items: flex-end;
}

.enlaces > a > i{
    font-size: 30px;
    margin-left: 20px;
}

.enlaces > a{
    text-decoration: none;
    color: white;
}

.enlaces > a:hover{
    color:#f90 ;
}


</style>