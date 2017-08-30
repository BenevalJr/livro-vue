<template>
	<div>
		<!-- Formulário de busca e resultado da busca -->
		<h3>Buscando rivais</h3>
	    <label>Time:</label>
	    <input type="text" v-model="busca">
	    <p>Rival: {{ rival(busca) }}</p>
	</div>
</template>

<script>
export default{
	name: 'lv-busca',
	data() {
		return {
			busca: ''
		}
	},
	methods: {
		// de acordo com o time retorna o resutado da busca, o que será seu rival
		rival(time) {
			switch( time.toLowerCase() ) {
				case 'corinthians':
					return 'palmeiras'
				case 'santos':
					return 'são paulo'
				case 'flamengo':
					return 'vasco'
				case 'cruzeiro':
					return 'em minas é marmelada'
				default:
					return 'não encontrado'
			}
		}
	}
}
</script>