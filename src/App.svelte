<script>
	import Header from "./shared/Header.svelte";
	import Content from "./shared/Content.svelte";
	import Button from "./shared/Button.svelte";
	import Input from "./shared/Input.svelte";
</script>

<Header>W.I.S. Support</Header>

<Content>
	<p>Hello, Human! Expirencing problems with W.I.S. or its surrounding services? Not to worry, I've got your back.</p>
	<p>Fill in basic information about you problem, your email, and a detailed description of your issue and i'll email you back ASAP</p>

	<form action="https://colorfall.000webhostapp.com/wissupport.php" method="POST">
		<select name="subject" required>
			<option value="technical-support">Tech Support</option>
			<option value="ban-appeal">Ban Appeal</option>
			<option value="cheat-report">Cheating Report</option>
			<option value="open-question">General Question</option>
		</select>
		<Input Required={true} Name="email" Placeholder="Email. Will be used to contact you" />
		<Input Required={true} Name="name" Placeholder="Your Name" />
		<Input Name="error" Placeholder="Error Code (if any)" />
		<Input Name="antivirus" Placeholder="Antivirus (if any, ex: McAfee, Nortan, etc...)" />

		<select name="platform" id="platform" required>
			<option value="none">(Select Platform)</option>
			<option value="steamvr-windows">SteamVR on Windows 10</option>
			<option value="steamvr-linux">SteamVR on Linux</option>
			<option value="quest">Oculus Quest</option>
			<option value="quest2">Oculus Quest 2</option>
		</select>

		<select name="headset" id="headset" style="display: none;">
			<option value="none">(Select VR Headset)</option>
			<option value="htc-vive">HTC Vive</option>
			<option value="htc-vive-pro">HTC Vive Pro</option>
			<option value="htc-vive-cosmos">HTC Vive Cosmos</option>
			<option value="valve-index">Valve Index</option>
			<option value="oculus-rift">Oculus Rift</option>
			<option value="oculus-rift-s">Oculus Rift S</option>
			<option value="quest">Oculus Quest (Oculus Link)</option>
			<option value="quest2">Oculus Quest 2 (Oculus Link)</option>
			<option value="other">Other...</option>
		</select>
		
		<select name="distro" id="distro" style="display: none;">
			<option value="none">(Select Distro)</option>
			<option value="ubuntu">Ubuntu</option>
			<option value="debian">Debian</option>
			<option value="mint">Linux Mint</option>
			<option value="fedora">Fedora</option>
			<option value="suse">SUSE</option>
			<option value="arch">Arch Linux</option>
			<option value="gentoo">Gentoo Linux</option>
			<option value="other">Other...</option>
		</select>

		<script>
			let getElement = (id) => {
				return document.getElementById(id);
			};
		
			let platformSelect = getElement("platform");
			function change() {
				getElement("headset").style.display = "none";
				getElement("distro").style.display = "none";
				if (platformSelect.value == "steamvr-windows" || platformSelect.value == "steamvr-linux") {
					getElement("headset").style.display = "block";
				}
				if (platformSelect.value == "steamvr-linux") {
					getElement("distro").style.display = "block";
				}
			}
			platformSelect.addEventListener("click", change);
		</script>

		<Input Multiline={true} Required={true} Name="problem" Placeholder="Describe the problem..." />
		<Button Type="formsubmit" Value="Submit" />
	</form>

	<p>Copyright © <a href="https://77Zsite.tk">77Z</a> 2021</p>
</Content>

<style>

	select {
		border-radius: 10px;
		width: 100%;
	}

</style>