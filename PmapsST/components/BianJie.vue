<template>
  <div class="container1">
     <div class="box1">
         <img src="../img/组21拷贝.png" alt="">
     </div>
     <div class="box2">
         <img src="../img/组399.png" alt="">
     </div>
     <div class="box3">
         <img src="../img/台子拷贝.png" alt="">
         <span>边界条件生成</span>
     </div>
     <div class="arrows1"></div>
     <div class="arrows2"></div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="less" scoped>
@keyframes Down {
    0%{
        transform: translate(-5%,-5%);
    }
    100%{
         transform: translate(5%,5%);
    }
}
@keyframes Up {
    0%{
        transform: translate(-5%,5%);
    }
    100%{
         transform: translate(5%,-5%);
    }
}
.container1{
position: relative;
width: 100%;
height: 100%;
.box1{
    position: absolute;
}
.box2{
    position: absolute;
    bottom: 40px;
    left: 50%;
    transform: translateX(-50%);
}
.box3{
    position: absolute;
    right: 40px;
    top: -250px;
    span{
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%,0%);
        color: #00eaff;
        font-size: 33px;
    }
}
.arrows1{
    position: absolute;
    bottom:200px ;
    left: 350px;
    width: 325px;
    height: 218px;
    background: url('../img/arrowsDown.png') no-repeat;
    animation:  Down 2s infinite linear;
}
.arrows2{
    position: absolute;
    right: 450px;
    bottom: 280px;
    width: 278px;
    height: 264px;
    background: url('../img/arrowsUP.png') no-repeat;
    animation:  Up 2s infinite linear;
}

}
</style>
