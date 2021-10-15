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

    <div id="app" v-if="false">
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
    <div id="app">
      <DataTable :items="desserts" :headers="headers">
        <template v-slot:header>
          <h2>Watch What You Eat!</h2>
        </template>
        <template v-slot:footer> Created 2021 by Robert Baumgartner </template>
        <template v-slot:bodyappend>
          <tr class="last-row">
            <td>Total</td>
            <td>{{ totalCalories }}</td>
            <td>{{ totalFat }}</td>
            <td>{{ totalCarbs }}</td>
            <td>{{ totalProtein }}</td>
            <td></td>
          </tr>
        </template>
      </DataTable>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Sheet from "@/components/Sheet.vue";
import AppLayout from "@/components/AppLayout.vue";
import AppButton from "@/components/AppButton.vue";
import DataTable from "@/components/Datatable.vue";

export default {
  name: "Home",
  components: {
    Sheet,
    AppLayout,
    AppButton,
    DataTable
  },
  data() {
    return {
      desserts: [
        {
          name: "pizza",
          calories: 345,
          fat: 6456,
          protein: 23435,
          carbohydrates: 34636,
          iron: 235
        },
        {
          name: "pizza2",
          calories: 346346,
          fat: 34534,
          protein: 235,
          carbohydrates: 346,
          iron: 45734
        },
        {
          name: "pizza3",
          calories: 2364,
          fat: 346,
          protein: 45345,
          carbohydrates: 3467457,
          iron: 245346
        },
        {
          name: "pizza4",
          calories: 4574357,
          fat: 4357347,
          protein: 3473657,
          carbohydrates: 4573437,
          iron: 4357347
        },
        {
          name: "pizza5",
          calories: 543737,
          fat: 437457,
          protein: 4577,
          carbohydrates: 4574357,
          iron: 45745
        },
        {
          name: "pizza6",
          calories: 35675,
          fat: 43534,
          protein: 34635,
          carbohydrates: 346345,
          iron: 435
        }
      ],
      headers: [
        "Name",
        "KCAL",
        "FAT(G)",
        "PROTEIN(G)",
        "CARBOHYDATES(G)",
        "IRON(%)"
      ]
    };
  },
  computed: {
    totalCalories() {
      let sum = 0;
      this.desserts.forEach(element => {
        sum += element.calories;
      });
      return sum;
    },
    totalProtein() {
      let sum = 0;
      this.desserts.forEach(element => {
        sum += element.protein;
      });
      return sum;
    },
    totalCarbs() {
      let sum = 0;
      this.desserts.forEach(element => {
        sum += element.carbohydrates;
      });
      return sum;
    },
    totalFat() {
      let sum = 0;
      this.desserts.forEach(element => {
        sum += element.fat;
      });
      return sum;
    }
  }
};
</script>
