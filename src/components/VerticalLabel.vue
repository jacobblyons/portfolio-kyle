<template>
    <div class="vertical-label">
        <div class="vertical-label-line">
            <svg height="20" width="5">
                <line x1="0" y1="0" x2="0" y2="20" style="stroke:rgb(255,255,255);stroke-width:4" />
            </svg>
        </div>
        <div>
            <p class="vertical-label-text" >{{title}}</p>
        </div>
        
    </div>
</template>

<style lang="scss" scoped>
.vertical-label {
  width: 100%;
  height: 100%;
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  justify-content: start;
  
  &-text {
    color: white;
    
    font: { 
        size:2em;
    };
    writing-mode: vertical-rl;
    text-orientation: sideways;
  }   
}
</style>

<script>
export default {
    name: "vertical-label",
    props: {
        title:String
    }
}
</script>

