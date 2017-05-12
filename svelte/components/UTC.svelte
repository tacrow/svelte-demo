<p>【Svelte】The time is ...</p>
<p>{{hours}}:{{leftPad(minutes, 2, '0')}}:{{leftPad(seconds, 2, '0')}}</p>

<script>
	import leftPad from 'left-pad'

	export default {
		helpers: {
			leftPad
		},
		computed: {
			hours: time => time.getHours(),
			minutes: time => time.getMinutes(),
			seconds: time => time.getSeconds()
		}
	}
</script>