<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3.0 + Vite" />
  <test/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import test from './components/test.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    test
  },

  setup () {
    // 假设本地机器无法做加减乘除运算，需要通过远程请求让服务端来实现。
    // 以加法为例，现有远程API的模拟实现

    const addRemote = async (a, b) => new Promise(resolve => {
      setTimeout(() => resolve(a + b), 1000)
      // return resolve(a + b)
    });

    // 请实现本地的add方法，调用addRemote，能最优的实现输入数字的加法。
    async function add(...inputs) {
      // 你的实现
      return inputs.reduce((promiseChain, item) => {
        return promiseChain.then(res => {
          return addRemote(res, item)
        })
      }, Promise.resolve(0))

      // return values
      // let res = 0;
      // if (inputs.length <= 2) return addRemote(...inputs)

      // for (const item of inputs) {
      //   res = await addRemote(res, item)
      // }

      // return res
    }

    // 请用示例验证运行结果:
    // console.log(new Date())
    add(1, 2)
      .then(result => {
        // console.log(result); // 3
        // console.log(new Date())
    });


    add(3, 5, 2)
      .then(result => {
        // console.log(result); // 10
    })

  },
  methods: {
  }
}
</script>
