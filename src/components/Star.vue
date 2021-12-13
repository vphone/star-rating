<template>
  <div>
    <div class="rate-area zero">
      <input type="radio" id="0-star" name="crating" value="0" aria-required="true">
      <label for="0-star" title="Poor">0 star</label>
    </div>
    <div class="rate-area">
      <input type="radio" id="5-star" name="crating" value="5">
      <label for="5-star" title="Amazing">5 stars</label>
      <input type="radio" id="4-star" name="crating" value="4">
      <label for="4-star" title="Good">4 stars</label>
      <input type="radio" id="3-star" name="crating" value="3">
      <label for="3-star" title="Average">3 stars</label>
      <input type="radio" id="2-star" name="crating" value="2">
      <label for="2-star" title="Not Good">2 stars</label>
      <input type="radio" id="1-star" required="" name="crating" value="1" aria-required="true">
      <label for="1-star" title="Bad">1 star</label>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Star',
  props: {
    active: Boolean
  }
}
</script>

<style scoped>
.rate-area {
  float:left;
  border-style: none;
}

.rate-area:not(:checked) > input {
  position:absolute;
  top:-9999px;
  clip:rect(0,0,0,0);
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
