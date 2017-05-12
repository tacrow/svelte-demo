<h2>App：</h2>
<p>{{hours}}:{{minutes}}:{{seconds}}</p>
<UTC time='{{time}}' />

<script>
	import UTC from './components/UTC.svelte'

	export default {
		data() {
			return {
				time: new Date()
			}
		},
		computed: {
			hours: time => time.getHours(),
			minutes: time => time.getMinutes(),
			seconds: time => time.getSeconds()
		},
		oncreate() {
			this.interval = setInterval(() => this.set({
				time: new Date()
			}), 1000)
		},
		ondestroy() {
			clearInterval(this.interval)
		},
		components: {
			UTC
		}
	}
</script>