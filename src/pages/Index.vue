<template>
  <q-page class="bg-custom-color">
   <div class="q-pa-md ">

    <div class="row">
      <div class="col-12 col-md-3 q-pa-md">
        <q-card :class="`my-card cc-card-1 card ${selectedCard === n ? 'active' : '' }`"
              v-for="n in 1" :key="n"
              @click="selectedCard = n">
        <q-card-section>
          Sales
          <div class="row q-pt-md">
            <div class="col-12 col-md-6">
              <span class="label-highlight sales">Test</span>
            </div>
            <div class="col-12 col-md-6">
              <span class="label-desc">Lifetime Sales</span>
              <h6 class="q-ma-none h6-result">P 175,000</h6>
              <span class="label-desc">Revenue Sales</span>
              <h6 class="q-ma-none h6-result">P 170,000</h6>
            </div>
            <q-separator inset />
            <div class="col-12">
              <span class="footer-card">Average Order Value</span>
              <span class="footer-card text-right">123413</span>
            </div>
          </div>
        </q-card-section>
      </q-card>
      </div>
      <div class="col-12 col-md-3 q-pa-md">
        <q-card :class="`my-card cc-card-1 card ${selectedCard === n ? 'active' : '' }`"
              v-for="n in 1" :key="n"
              @click="selectedCard = n">
        <q-card-section>
          Engagement
          <div class="row q-pt-md">
            <div class="col-12 col-md-6">
              <span class="label-highlight engagement">Test</span>
            </div>
            <div class="col-12 col-md-6">
              <span class="label-desc">Lifetime SMS Engagement</span>
              <h6 class="q-ma-none h6-result">285</h6>
              <span class="label-desc">Daily Average</span>
              <h6 class="q-ma-none h6-result">57</h6>
            </div>
            <q-separator inset />
            <div class="col-12">
              <span class="footer-card">20% decrease in 30 days</span>
            </div>
          </div>
        </q-card-section>
      </q-card>
      </div>
      <div class="col-12 col-md-3 q-pa-md">
        <q-card :class="`my-card cc-card-1 card ${selectedCard === n ? 'active' : '' }`"
              v-for="n in 1" :key="n"
              @click="selectedCard = n">
        <q-card-section>
          Acquisition
          <div class="row q-pt-md">
            <div class="col-12 col-md-6">
              <span class="label-highlight acquisition">Test</span>
            </div>
            <div class="col-12 col-md-6">
              <span class="label-desc">Registered Users</span>
              <h6 class="q-ma-none h6-result">285</h6>
              <span class="label-desc">Daily Average</span>
              <h6 class="q-ma-none h6-result">57</h6>
            </div>
            <q-separator inset />
            <div class="col-12">
              <span class="footer-card">20% decrease in 30 days</span>
            </div>
          </div>
        </q-card-section>
      </q-card>
      </div>
      <div class="col-12 col-md-3 q-pa-md">
        <q-card :class="`my-card cc-card-1 card ${selectedCard === n ? 'active' : '' }`"
              v-for="n in 1" :key="n"
              @click="selectedCard = n">
        <q-card-section>
          Rewards Program
          <div class="row q-pt-md">
            <div class="col-12 col-md-6">
              <span class="label-highlight rewards">Test</span>
            </div>
            <div class="col-12 col-md-6">
              <span class="label-desc">Rewards Redeemed</span>
              <h6 class="q-ma-none h6-result">175,000</h6>
              <span class="label-desc">Issued Rewards</span>
              <h6 class="q-ma-none h6-result">175,000</h6>
            </div>
            <q-separator inset />
            <div class="col-12">
              <span class="footer-card">20% decrease in 30 days</span>
            </div>
          </div>
        </q-card-section>
      </q-card>
      </div>
    </div>
    <!-- Sales overview Chart -->
    <div class="row">
      <div class="col-12 q-pa-md">
         <q-card class="my-card cc-card-1">
           <h6 class="q-pa-md q-mt-none t-sales">Sales Overview
            <div class="float-right">
              <q-btn-dropdown label="All Transactions" class="q-mr-md">
              <q-list>
                <q-item clickable v-close-popup @click="onItemClick">
                  <q-item-section>
                    <q-item-label>Photos</q-item-label>
                  </q-item-section>
                </q-item>

                <q-item clickable v-close-popup @click="onItemClick">
                  <q-item-section>
                    <q-item-label>Videos</q-item-label>
                  </q-item-section>
                </q-item>

                <q-item clickable v-close-popup @click="onItemClick">
                  <q-item-section>
                    <q-item-label>Articles</q-item-label>
                  </q-item-section>
                </q-item>
              </q-list>
            </q-btn-dropdown>
            <!-- -- -->
            <q-btn-dropdown label="All Branches">
              <q-list>
                <q-item clickable v-close-popup @click="onItemClick">
                  <q-item-section>
                    <q-item-label>Photos</q-item-label>
                  </q-item-section>
                </q-item>

                <q-item clickable v-close-popup @click="onItemClick">
                  <q-item-section>
                    <q-item-label>Videos</q-item-label>
                  </q-item-section>
                </q-item>

                <q-item clickable v-close-popup @click="onItemClick">
                  <q-item-section>
                    <q-item-label>Articles</q-item-label>
                  </q-item-section>
                </q-item>
              </q-list>
            </q-btn-dropdown>
            </div>

           </h6>

          <q-card-section>
            <column-chart
            :data="[
            ['Aug 1',  10000], ['Aug 2', 20000], ['Aug 3', 30000]
            ]
            "></column-chart>
            <!-- <apexchart type="bar" height="350" :series="series"></apexchart> -->
          </q-card-section>
        </q-card>
      </div>
    </div>
    <!-- Branch Performance -->
    <div class="row">
      <div class="col-12 col-md-6 q-pa-md">
         <q-card class="my-card cc-card-1">
          <q-card-section class="q-pa-none">
             <q-table class="table"
                title="Branch Selection"
                dense
                :data="data"
                :columns="columns"
                row-key="name"
              />
          </q-card-section>
        </q-card>
      </div>
      <div class="col-12 col-md-6 q-pa-md">
         <q-card class="my-card cc-card-1">
            <q-card-section class="q-pa-none">
              <q-table class="table"
                title="Rewards Performance"
                dense
                :data="data"
                :columns="columns"
                row-key="name"
              />
            </q-card-section>
          </q-card>
      </div>
    </div>

  </div>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',

  data () {
    return {
      selectedCard: 0,

      columns: [
        {
          name: 'name',
          required: true,
          label: 'Branch',
          align: 'left',
          field: row => row.name,
          format: val => `${val}`,
          sortable: true
        },
        { name: 'tsales', align: 'center', label: 'Total Sales', field: 'tsales', sortable: true },
        { name: 'stats', label: '', field: 'stats', sortable: true }
      ],
      data: [
        {
          name: 'Makati',
          tsales: '5,000.00',
          stats: '20%'
        },
        {
          name: 'BGC Taguig',
          tsales: '4,000.00',
          stats: '10.52%'
        }
      ]

    }
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Muli&display=swap');

.label-highlight {
  color: #fff;
  padding: 3px 10px;
  border-radius: 20px;
}

.label-highlight.rewards {
  background:#e1bee7!important;
}

.label-highlight.acquisition {
  background:#ffe082!important;
}

.label-highlight.engagement {
  background:#64ffda!important;
}

.label-highlight.sales {
  background:#4fc3f7!important;
}

.q-separator--horizontal.q-separator--inset{
  margin: 5px 1px;
}

.text-right {
  text-align: right;
}

.label-desc{
  font-size: 12px;
  color: #909090;
  text-align: right;
  display: block;
}

.footer-card {
  font-size:10px;
  color: #909090;
  display: block;
}

.h6-result {
  text-align: right;
}

.t-sales {
  background: #e9ebf5;
}
.card:active {
  box-shadow: 0px 0px 11px 6px #b6b6ed63;
}
.active {
  box-shadow: 0px 0px 11px 6px #b6b6ed63;
  cursor: pointer;
}
body{
  font-family: 'Muli', sans-serif;
}
  .q-layout__section--marginal{
    color: #000;
  }
.bg-custom-color{
  background: #f4f5f9;
}
.my-card {
  box-shadow: none;
}

.table {
  box-shadow: none;
}

.q-table__container > div:first-child {
  background: #e9ebf5;
}

.q-table--dense .q-table__top {
      padding: 12px 15px;
}

.q-table--dense .q-table tbody tr,
.q-table--dense .q-table thead th,
.q-table--dense .q-table__bottom
{
  height: 50px;
}

</style>
