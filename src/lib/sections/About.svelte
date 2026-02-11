<script>
	import { locale, _ } from 'svelte-i18n';
</script>

<div
	class="grid items-center bg-gradient-to-b from-[#0000005b] to-[#5252525b] pb-12 pt-16 text-white md:ml-10 md:min-h-[100svh] md:grid-cols-3 md:items-start"
>
	{#if $locale === 'th'}
		<div class="flex flex-col items-center md:w-11/12 md:items-start xl:pl-12">
			<div class="mb-6 flex flex-col items-center md:items-start">
				<img
					src="/AW_LOGO_PKDC-05 1.png"
					alt="Logo"
					class="h-auto w-[200px] max-w-xs md:h-[116px] md:w-[199px]"
				/>
			</div>
			<ul class="text-center md:text-left">
				<li><span class="font-bold">Generative AI:</span></li>
				<li>ชยภัทร อาชีวระงับโรค</li>
				<li>ภูมิปรินทร์ มะโน</li>
				<li>ปิยพร พงษ์ทอง</li>
				<li>พิเชษฐ์ กลั่นชื่น</li>
				<li>พัทธ์ ภัทรานุธาพร</li>
				<li>กรกาญจน์ รุ่งสว่าง</li>
				<li>ธนพล สุขสมรูป</li>
			</ul>
		</div>

		<div class="flex flex-col items-center space-y-6 p-6 md:w-11/12 md:items-start md:p-0">
			<ul class="text-center md:text-left">
				<li><span class="font-bold">Artist/Choreographer/Director:</span></li>
				<li>พิเชษฐ์ กลั่นชื่น</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Technology Advisors::</span></li>
				<li>พัทธ์ ภัทรานุธาพร</li>
				<li>ภูมิปรินทร์ มะโน</li>
				<li>ชยภัทร อาชีวระงับโรค</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Dancers:</span></li>
				<li>กรกาญจน์ รุ่งสว่าง</li>
				<li>ธรรศ จงจัดกลาง</li>
				<li>สุนนท์ วชิรรวราการ</li>
				<li>จุฬาลักษณ์ เอกวัฒนพันธ์</li>
			</ul>
		</div>

		<div class="flex flex-col items-center space-y-6 p-6 md:w-11/12 md:items-start md:p-0">
			<ul class="text-center md:text-left">
				<li><span class="font-bold">Video Production:</span></li>
				<li>ตรีเทพโปรดักชั่น</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Website & LMS:</span></li>
				<li>ปภัสสิริย์ อภิไพบูลย์</li>
				<li>รินรดา เทพแก้ว</li>
				<li>ไท ปังสกุลยานนท์</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Management & Support Team:</span></li>
				<li>โศจิรัตน์ สิงหลกะ</li>
				<li>กันต์พงศ์ ทวีสุข</li>
				<li>ผดุง จุมพันธ์</li>
			</ul>
		</div>
	{:else}
		<div class="flex flex-col items-center md:w-11/12 md:items-start xl:pl-12">
			<div class="mb-6 flex flex-col items-center md:items-start">
				<img
					src="/AW_LOGO_PKDC-05 1.png"
					alt="Logo"
					class="h-auto w-[200px] max-w-xs md:h-[116px] md:w-[199px]"
				/>
			</div>
			<ul class="text-center md:text-left">
				<li><span class="font-bold">Generative AI:</span></li>
				<li>Chayapatr Archiwaranguprok</li>
				<li>Phoomparin Mano</li>
				<li>Piyaporn Bhongse-tong</li>
				<li>Pichet Klunchun</li>
				<li>Pat Pataranutaporn</li>
				<li>Kornkarn Rungsawang</li>
				<li>Thanapon Suksomroop</li>
			</ul>
		</div>

		<div class="flex flex-col items-center space-y-6 p-6 md:w-11/12 md:items-start md:p-0">
			<ul class="text-center md:text-left">
				<li><span class="font-bold">Artist/Choreographer/Director:</span></li>
				<li>Pichet Klunchun</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Technology Advisors::</span></li>
				<li>Pat Pataranutaporn</li>
				<li>Phoomparin Mano</li>
				<li>Chayapatr Archiwaranguprok</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Dancers:</span></li>
				<li>Kornkarn Rungsawang</li>
				<li>Tas Chongchadklang</li>
				<li>Sunon Wachirawarakarn</li>
				<li>Julaluck Eakwattanapun</li>
			</ul>
		</div>

		<div class="flex flex-col items-center space-y-6 p-6 md:w-11/12 md:items-start md:p-0">
			<ul class="text-center md:text-left">
				<li><span class="font-bold">Video Production:</span></li>
				<li>Threethep Production</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Website & LMS:</span></li>
				<li>Papatsiri Apipaiboon</li>
				<li>Rinrada Thepkaew</li>
				<li>Thai Pangsakulyanont</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Management & Support Team:</span></li>
				<li>Sojirat Singholka</li>
				<li>Kanpong Thaweesuk</li>
				<li>Padung Jumpan</li>
			</ul>
		</div>
	{/if}

	<!-- Partner section -->
	<div class="col-span-full mt-12 grid grid-cols-1 gap-12 px-6 pb-12 pt-12 md:grid-cols-2 md:pl-12">
		<!-- About this project - Left column -->
		<div class="flex flex-col items-center text-center md:items-start md:text-left">
			<h2 class="mb-6 text-2xl font-bold text-white md:text-3xl">
				{$_('partners.about_title')}
			</h2>
			<p class="max-w-xl text-base leading-relaxed text-white/90 md:text-lg">
				{$_('partners.about_text')}
			</p>
		</div>

		<!-- Partner & Supporters - Right column -->
		<div class="flex flex-col items-center">
			<h2 class="mb-8 text-2xl font-bold text-white md:text-3xl">
				{$_('partners.title')}
			</h2>
			<div class="flex flex-wrap items-center justify-center gap-8 md:gap-12">
				<img
					src="/Thai-media-logo.png"
					alt="Thai Media Fund"
					class="h-[120px] w-auto object-contain md:h-[180px]"
				/>
				<img
					src="/tkpark-logo.png"
					alt="TK Park"
					class="h-[120px] w-auto object-contain md:h-[180px]"
				/>
			</div>
		</div>
	</div>
</div>
