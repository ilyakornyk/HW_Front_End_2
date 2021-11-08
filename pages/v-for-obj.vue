<template>
  <div>
    <Navbar />
    <div class="container">
		<ul class="list-group col-md-6 offset-3">
			<p class="text-primary fs-3 text-center">{{title}}</p>
			<li class="list-group-item list-group-horizontal" v-for="(value, name) in object" >
				{{name}}: {{value}}
			</li>
		</ul>
	</div>
  </div>
</template>

<script>

export default ({
	data () {
		return {
			object: {
				'title': 'The Dark Knight',
				'year': 2008,
				'director': 'Christopher Nolan',
				'budget': '$185 million',
				'box office': '1.005 billion'
			},
			title: 'V-for for object'
		}
	}
})
</script>

