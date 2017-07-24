    <style>
    body {
  padding-top: 10px;
  padding-left: 5px;
}
button {
  background: white;
  border: 1px #ddd solid;
  width: 130px;
  height: 40px;
  font-size: 16px;
  color: #222;
  outline: 0;
  cursor: pointer;
}

button.active {
  background: red;
  color: white;
}
    </style>
	
<template>
<table class="q-table">
  <thead>
    <tr>
      <th class="text-left"></th>
      <th class="text-right"></th>
      <th class="text-right"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="text-left"> <button class="like-button" :class="{ 'active': active }" @click="liked">{{ active ? likedText : buttonText }}</button></td>
      <td class="text-right"> <button class="like-button" :class="{ 'active': active }" @click="liked">{{ active ? likedText : buttonText }}</button></td>
      <td class="text-right"> <button class="like-button" :class="{ 'active': active }" @click="liked">{{ active ? likedText : buttonText }}</button></td>
    </tr>
    <tr>
      <td class="text-left"> <button class="like-button" :class="{ 'active': active }" @click="liked">{{ active ? likedText : buttonText }}</button></td>
      <td class="text-right"> <button class="like-button" :class="{ 'active': active }" @click="liked">{{ active ? likedText : buttonText }}</button></td>
      <td class="text-right"> <button class="like-button" :class="{ 'active': active }" @click="liked">{{ active ? likedText : buttonText }}</button></td>
    </tr>
    <tr>
      <td class="text-left"> <button class="like-button" :class="{ 'active': active }" @click="liked">{{ active ? likedText : buttonText }}</button></td>
      <td class="text-right"> <button class="like-button" :class="{ 'active': active }" @click="liked">{{ active ? likedText : buttonText }}</button></td>
      <td class="text-right"> <button class="like-button" :class="{ 'active': active }" @click="liked">{{ active ? likedText : buttonText }}</button></td>
    </tr>
  </tbody>
</table>
       
</template>

<script>
export default {

  data () {
    return {
      active: false,
      buttonText: 'Available',
      likedText: 'Unvailable'
    }
  },
  methods: {
    liked () {
      this.active = !this.active
    }
  }
}
</script>
