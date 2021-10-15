<template>
  <div>
    <div style="display:flex" v-if="false">
      <Sheet style="margin-left:20px">
        <h3>Memo to myself</h3>
        <p>Always prepare for PLFs in time!</p>
        <img src="info.svg" width="80px" />
      </Sheet>
      <Sheet style="margin-left:20px">
        <p>INSY, SEW and Webtechnologies are our favorite subjects!</p>
        <span style="font-style: italic"
          >Starkschwitz Fiedler, Jan Schreck</span
        >
        <p>Wish i was there!</p>
        <span style="font-style: italic">E. Wahn</span>
      </Sheet>
    </div>

    <div id="app" v-if="true">
      <!-- Die Reihenfolge ist egal -->
      <AppLayout>
        <template v-slot:header>
          I was made with Vue slots!
        </template>
        <template v-slot:default>
          <AppButton><img src="home.svg" /> Home</AppButton>
        </template>
        <template v-slot:footer>
          By Robert Baumgartner
        </template>
      </AppLayout>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Sheet from "@/components/Sheet.vue";
import AppLayout from "@/components/AppLayout.vue";
import AppButton from "@/components/AppButton.vue";

export default {
  name: "Home",
  components: {
    Sheet,
    AppLayout,
    AppButton
  }
};
</script>
