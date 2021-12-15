
<script>
export default {
    name:"Child",
    data() {
        return{
            message:"That's what she said",
        }
    },
    methods: {
        sendMessageToParent(){
            //Emitimos el evento con sus eventargs
            this.$emit("my-message", this.message)
        }
    },
    mounted(){
        this.sendMessageToParent()
    }

}
</script>

<style>

</style>