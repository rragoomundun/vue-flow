<template>
  <div>
    <div id="drawing-interface">
      <div>
        <div>
          <p><b>Events</b></p>

          <flowy-new-block
            v-for="(block, index) in eventBlocks"
            :key="index"
            class="q-mr-md"
          >
            <template v-slot:preview="{}">
              <block-name
                :title="block.title"
                :description="block.description"
              />

              <demo-block
                :title="block.preview.title"
                :description="block.preview.description"
              />
            </template>
          </flowy-new-block>

          <!-- <flowy-new-block
          v-for="(block, index) in eventBlocks"
          :key="index"
          class="q-mr-md"
        >
          <template>
            <demo-block
              :title="block.preview.title"
              :description="block.preview.description"
            />
          </template>
        </flowy-new-block> -->

          <!-- <flowy-new-block
          v-for="(event, index) in eventBlocks"
          :key="index"
          class="q-mr-md"
          @drag-start="onDragStartNewBlock"
          @drag-stop="onDragStopNewBlock"
        >
          <template v-slot:preview="{}">
            <demo-block
              :title="block.preview.title"
              :description="block.preview.description"
            />
          </template>
          <template v-slot:node="{}">
            <demo-node
              :title="block.node.title"
              :description="block.node.description"
              :custom-attribute="block.node.canBeAdded"
            />
          </template>
        </flowy-new-block> -->
        </div>

        <div>
          <p><b>Actions</b></p>
        </div>
      </div>

      <div>
        <h1 style="text-align: center">TEXT CENTER</h1>
      </div>
    </div>
  </div>
</template>

<style scoped>
#drawing-interface {
  display: flex;
  font-family: sans-serif;
}

#drawing-interface > div:first-child {
  min-width: 256px;
  max-width: 256px;
  border-right: 1px dashed #aaa;
}

#drawing-interface > div:first-child p {
  text-align: center;
}

#drawing-interface > div:last-child {
  flex-grow: 1;
  width: auto;
}
</style>

<script>
import Vue from "vue";
import FlowyPlugin from "@hipsjs/flowy-vue";

// import BlockName from "./BlockName.vue";

import "@hipsjs/flowy-vue/dist/lib/flowy-vue.css";

Vue.use(FlowyPlugin);

export default {
  name: "DrawingInterface",
  components: {
    // BlockName,
  },
  data: () => ({
    eventBlocks: [
      {
        title: "New visitor",
        description:
          "<span>When a <b>new visitor</b> goes to <b>Site 1</span></span>",
      },
    ],
  }),

  // data: {
  //   eventBlocks: [
  //     {
  //       preview: {
  //         title: "New visitor",
  //       },
  //       node: {
  //         title: "New visitor",
  //         description:
  //           "<span>When a <b>new visitor</b> goes to <b>Site 1</span></span>",
  //       },
  //     },
  //   ],
  //   actionBlocks: [{}],
  // },
};
</script>
