<template>
    <div style="background-color: grey">
        <div class="box-el" :class="{'active':isrotate}">
            <div>
                <img src="./logo.png" alt="">
            </div>
            <div>
                <img src="./pic-logo.png" alt="">
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'imgRotate',
  data () {
    return {
      isrotate: false
    }
  },
  created () {
    setInterval(() => {
      this.isrotate = !this.isrotate
    }, 2000)
  }
}
</script>

<style scoped lang="scss">
    .box-el{
        background-color: grey;
        transition: transform 1s linear;
        width: 56px;height: 39px;
        >div{
            width: 56px;height: 39px;
            text-align: center;
            background-color: grey;
            position: absolute;
            top: 0;
            left: 0;
            color: #fff;
            transition: .8s ease-in-out;
            overflow: hidden;
        }
    }
    .box-el >div:first-child{
        transform: rotateY(0);
        z-index: 2;
    }
    .box-el >div:last-child{
        transform: rotateY(180deg);
        z-index: 1;
    }
    .active >div:first-child{
        transform: rotateY(180deg);
        z-index: 1;
    }
    .active >div:last-child{
        transform: rotateY(0);
        z-index: 2;
    }
</style>
