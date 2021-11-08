<template>
  <div>
    <Navbar />
    <div class="container">
		<ul class="list-group col-md-6 offset-3 text-center">
			<p class="text-primary fs-3 text-center">{{title}}</p>
			<li class="list-group-item" v-for="(item, id) in array" :key="id">
				{{item}}
			</li>
		</ul>
	</div>
  </div>
</template>

<script>

export default ({
	data () {
		return {
			array: ['some text', 'Lord of the rings', 'Harry Potter', 'Racing car', '2021', 'JavaScript'],
			title: 'V-for for array'
		}
	}
})
</script>

