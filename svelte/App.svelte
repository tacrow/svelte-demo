<p>【Svelte】The time is ...</p>
<p>{{hours}}:{{leftPad(minutes, 2, '0')}}:{{leftPad(seconds, 2, '0')}}</p>
<UTC time='{{time}}' />

<script>
	import UTC from './components/UTC.svelte'
	import leftPad from 'left-pad'

	export default {
		helpers: {
			leftPad
		},
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