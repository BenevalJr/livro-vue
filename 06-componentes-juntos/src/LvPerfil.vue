<template>
	<div>
		<!-- Exibe dados do time -->
		<h3>Perfil</h3>
	    <p>Time: {{ nome }}</p>
	    <p>Estádio: {{ estadio }}</p>
	</div>
</template>

<script>
export default{
	name: 'lv-perfil',
	data() {
		// inicia com dados do Cruzeiro de BH
		return {
			nome: 'Cruzeiro',
			estadio: 'Mineirão',
		}
	},
}
</script>