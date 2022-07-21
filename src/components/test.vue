<template>
  <div>
    <ul ref="ul1" id="list1">
      <li key="a">a</li>
      <li key="b">b</li>
      <li key="c">c</li>
    </ul>
    <ul ref="ul2" id="list2">
      <li key="a">a</li>
      <li key="b">b</li>
      <li key="haha">haha</li>
    </ul>
  </div>
</template>

<script>
export default {
  components: {
  },

  props: {
  },

  data () {
    return {
      oldVDOM: {
        tagName: 'ul',
        props: {
          id: 'list1'
        },
        children: [
          {
            tagName: 'li',
            key: 'a',
            props: {},
            children: ['a']
          },
          {
            tagName: 'li',
            key: 'b',
            props: {},
            children: ['b']
          },
          {
            tagName: 'li',
            key: 'c',
            props: {},
            children: ['c']
          }
        ]
      },
      newVDOM: {
        tagName: 'ul',
        props: {
          id: 'list1'
        },
        children: [
          {
            tagName: 'li',
            key: 'a',
            props: {},
            children: ['a']
          },
          {
            tagName: 'li',
            key: 'b',
            props: {},
            children: ['b']
          },
          {
            tagName: 'li',
            key: 'haha',
            props: {},
            children: ['haha']
          }
        ]
      }
    }
  },

  computed: {
  },

  methods: {
  },

  mounted () {
    console.log(this)
  }
}
</script>
