<template>
  <div class="about">
    <div class="statistic">
      <div class="allFlat">
        <h4>Всего квартир</h4>
        <p><span>300</span>квартир</p>
      </div>
      <div class="allFlat">
        <h4>Проданно квартир</h4>
        <div class="card_content">
          <v-progress-circular
            :rotate="360"
            :size="100"
            :width="15"
            :value="valueOne"
            color="white"
          >
            {{ valueOne }} %
          </v-progress-circular>
          <p><span>120</span>квартир</p>
        </div>
      </div>
      <div class="allFlat">
        <h4>Просмотр квартир</h4>
        <div class="card_content">
          <v-progress-circular
            :rotate="360"
            :size="100"
            :width="15"
            :value="valueTwo"
            color="white"
          >
            {{ valueTwo }} %
          </v-progress-circular>
          <p><span>160</span>квартир</p>
        </div>
      </div>
    </div>
    <div class="filter">
      <div class="idtest">
        <v-text-field label="Id" type="number"></v-text-field>
      </div>
      <p class="nameFlat">Название</p>
      <div class="testCout">
        <v-select
          v-model="e7"
          :items="states"
          label="Комнат"
          multiple
          chips
          persistent-hint
        ></v-select>
      </div>
      <div class="testStatus">
        <v-select
          v-model="e7"
          :items="status"
          label="Статус"
          multiple
          chips
          persistent-hint
        ></v-select>
      </div>
      <div class="testPrice" style="width: 12%">
        <div class="valueMinMax">
          <v-text-field label="От" type="number"></v-text-field>
        </div>
        <span>-</span>
        <div class="valueMinMax">
          <v-text-field label="до" type="number"></v-text-field>
        </div>
      </div>
      <p>Подробней</p>
    </div>
    <div class="table" v-for="flat in flats" :key="flat.id">
      <p class="idTable">{{ flat.id }}</p>
      <p class="nameFlat">{{ flat.name }}</p>
      <p class="testCout">{{ flat.room }} комната</p>
      <p class="testStatus">{{ flat.status }}</p>
      <p class="testPrice">{{ flat.price }} грн</p>
      <v-btn elevation="0" style="padding: 3px">Больше</v-btn>
    </div>
  </div>
</template>
<script>
export default {
  name: "AboutView",
  data() {
    return {
      e7: [],
      states: ["1 комната", "2 комнаты", "3 комнаты", "4 комнаты"],
      status: ["Свободная", "Просмотр", "Проданна"],
      interval: {},
      valueOne: 40,
      valueTwo: 60,
      flats: [
        {
          id: 1,
          name: "Однокомнатная квартира",
          room: 1,
          description: "Тут будет описание",
          status: "Свободная",
          price: 10000,
        },
        {
          id: 2,
          name: "Двух комнатная квартира",
          room: 2,
          description: "Тут будет описание",
          status: "Просмотр",
          price: 10000,
        },
        {
          id: 3,
          name: "Трехкомнатная квартира",
          room: 3,
          description: "Тут будет описание",
          status: "Просмотр",
          price: 10000,
        },
        {
          id: 4,
          name: "Четырехкомнатрая квартира",
          room: 4,
          description: "Тут будет описание",
          status: "Свободная",
          price: 10000,
        },
      ],
    };
  },
};
</script>
<style>
.about {
  margin: 10px 100px;
}
.filter {
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  column-gap: 20px;
  align-items: flex-end;
}
.table {
  border-radius: 4px;
  display: flex;
  column-gap: 20px;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  margin-bottom: 20px;
  padding: 0 5px;
}
.statistic {
  display: flex;
  justify-content: space-between;
  margin-bottom: 50px;
}
.allFlat {
  background: #36452f;
  box-shadow: 0px 4px 7px rgba(0, 0, 0, 0.25);
  border-radius: 4px;
  width: 500px;
  height: 200px;
  padding: 20px 30px;
  display: flex;
  justify-content: space-between;
  flex-direction: column;
}
.allFlat h4 {
  font-weight: 700;
  font-size: 35px;
  color: #e08652;
}
.allFlat span {
  font-weight: 700;
  font-size: 50px;
  color: #e08652;
  margin-right: 15px;
}
.allFlat p {
  margin: 0;
  font-size: 20px;
  color: white;
}
.card_content {
  display: flex;
  align-items: flex-end;
  column-gap: 20px;
}
.idtest,
.idTable {
  width: 150px;
}
.nameFlat {
  width: 300px;
}
.testCout {
  width: 440px;
}
.testStatus {
  width: 420px;
}
.testPrice {
  display: flex;
  flex-direction: row;
  column-gap: 20px;
  align-items: center;
  width: 12%;
}
.valueMinMax {
  width: 80px;
}
</style>
