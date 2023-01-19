<template>
    <div id="app">
        <VueDragResize :isActive="true" :w="200" :h="200" v-on:resizing="resize" v-on:dragging="resize">
           
            <p>{{ top }} х {{ left }} </p>
            <p>{{ width }} х {{ height }}</p>
        </VueDragResize>
    </div>
</template>

<script lang="ts">
    import VueDragResize from 'vue-drag-resize/src/component/vue-drag-resize.vue';

    export default {
        name: 'app',

        components: {
            VueDragResize
        },

        data() {
            return {
                width: 0,
                height: 0,
                top: 0,
                left: 0
            }
        },

        methods: {
            resize(newRect:any) {
                this.width = newRect.width;
                this.height = newRect.height;
                this.top = newRect.top;
                this.left = newRect.left;
            }
        }
    }
</script>