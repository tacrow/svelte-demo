<h2>UTC：</h2>
<p>{{hours}}:{{minutes}}:{{seconds}}</p>

<script>
	export default {
		computed: {
			hours: time => time.getHours(),
			minutes: time => time.getMinutes(),
			seconds: time => time.getSeconds()
		}
	}
</script>