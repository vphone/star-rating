<template>
  <div>
    <div class="rate-area zero">
      <input type="radio" id="0-star" name="crating" value="0" aria-required="true">
      <label for="0-star" title="Poor">0 star</label>
    </div>
    <div class="rate-area">
    <template v-for="item in stars">
      <input type="radio" :id="`${item.id}-star`" :key="`input-${item.id}`" name="crating" :value="item.id">
      <label :for="`${item.id}-star`" :key="`label-${item.id}`"  :title="item.title">{{ item.title}}</label>
    </template>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Star',
  props: {
    active: Boolean
  },
  data() {
    return {
      stars: [
      {
        id: 5,
        label: 'stars',
        title: 'Amazing'
      },
      {
        
        id: 4,
        label: 'stars',
        title: 'Good'
      },
      {
        id: 3,
        label: 'stars',
        title: 'Average'
      },
      {
        id: 2,
        label: 'stars',
        title: 'Not good'
      },
      {
        id: 1,
        label: 'star',
        title: 'Bad'
      },]
    }
  },
}
</script>

<style scoped>
.rate-area {
  float:left;
  border-style: none;
}

.rate-area:not(:checked) > input {
  display: none;
}

.rate-area:not(:checked) > label {
  float: right;
  width: .80em;
  overflow: hidden;
  white-space: nowrap;
  cursor: pointer;
  font-size: 40px;
  line-height: 32px;
  color: lightgrey;
  margin-bottom: 10px !important;
}

.rate-area:not(:checked) > label:before {
  content: '★';
}

.rate-area > input:checked ~ label {
  color: #FFD700;
  text-shadow: none;
}

.rate-area:not(:checked) > label:hover,
.rate-area:not(:checked) > label:hover ~ label {
  color: #FFD700;
}

.rate-area > input:checked + label:hover,
.rate-area > input:checked + label:hover ~ label,
.rate-area > input:checked ~ label:hover,
.rate-area > input:checked ~ label:hover ~ label,
.rate-area > label:hover ~ input:checked ~ label {
  color: #FFD700;
  text-shadow: none;
}

.zero > input:checked ~ label,
.zero:not(:checked) > label:hover,
.zero:not(:checked) > label:hover ~ label,
.zero > input:checked + label:hover,
.zero > input:checked ~ label:hover {
  color: black;
}
.rate-area > label:active {
  position:relative;
  top:0px;
  left:0px; 
}
</style>
