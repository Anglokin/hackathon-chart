<template>
  <div class="greetings">
    <D3Sunburst :config="chart_config" :datum="chart_data"></D3Sunburst>
  </div>
</template>

<script>
import { D3Sunburst } from 'vue-d3-charts';

export default {
  components: {
    D3Sunburst,
  },
  data() {
    return {
      chart_data: [
        {
          name: 'one',
          children: [
            {
              name: 'two',
              children: [
                {
                  name: 'three',
                  value: 2354,
                },
                {
                  name: 'four',
                  value: 1384,
                },
              ],
            },
          ],
        },
      ],
      chart_config: {
        key: 'name',
        value: 'value',
        color: {
          scheme: ['#55D6BE', '#ACFCD9', '#7D5BA6', '#DDDDDD', '#FC6471'],
        },
        margin: {
          top: 20,
          right: 20,
          bottom: 20,
          left: 20,
        },
        transition: {
          duration: 450,
          ease: 'easeBounceOut',
        },
      },
    };
  },

  props: {
    msg: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
.greetings {
  width: 100%;
}
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    display: block;
    text-align: left;
  }
}
</style>
