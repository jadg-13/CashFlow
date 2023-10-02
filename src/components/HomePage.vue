<template>
  <Layout>
    <template #header>
      <Header></Header>
    </template>
    <template #resume>
      <Resume :label="'Ahorro Total'" :amount="amount" :total-amount="totalAmount">
        <template #graphic>
          <Graphic :amounts="amounts"/>
        </template>
        <template #action><Action/></template>
      </Resume>
    </template>
    <template #movements>
      <Movements 
      :movements="movements"
      />
    </template>
  </Layout>
</template>

<script>
import Layout from './LayoutPage.vue';
import Header from './HeaderPage.vue';
import Resume from './Resume/IndexR'
import Movements from './Movements/IndexM.vue';
import Action from './ActionModel.vue';
import Graphic from './Resume/GraphicR.vue';
export default {
  components: {
    Layout,
    Header,
    Resume,
    Movements,
    Action,
    Graphic,
},
  data() {
    return {
      label: null,
      amount: null,
      totalAmount: 0,
      amounts:[300, 200, 350, -50, 562, 556, 100, 300, -20, 230],
      movements: [
        {
          id: 1,
          title: "Deposito 1",
          description: "Pago mensual",
          amount: 100,
        },
        {
          id: 2,
          title: "Deposito 2",
          description: "Pago mensual",
          amount: 100,
        },
        {
          id: 3,
          title: "Deposito 3",
          description: "Pago mensual",
          amount: 100,
        },
        {
          id: 4,
          title: "Deposito 4",
          description: "Pago mensual",
          amount: 100,
        },
      ]
    }
  },
};
</script>