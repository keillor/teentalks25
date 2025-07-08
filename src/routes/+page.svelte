<script>
	import { Button, buttonVariants } from '$lib/components/ui/button/index.js';
	import * as Dialog from '$lib/components/ui/dialog/index.js';
	import { Input } from '$lib/components/ui/input/index.js';
	import { Label } from '$lib/components/ui/label/index.js';

	const lectures = [
		{
			title: "What's in your suitcase?",
			month: 'January',
			day: '12th',
			speaker: 'Barbara Blackwell',
			imgUrl: '/barbara.png',
			youtube: 'https://youtu.be/yWzu94zdub4',
			desc: 'Barbara as Chief Executive of Principia, has 35 years administrative experience in both private liberal arts colleges and secondary schools. She earned her bachelor’s degree from Allegheny College and law degree from the University of Pittsburgh Law School. She has extensive experience in higher education and independent K–12 education.'
		},
		{
			title: 'Your identity and Purpose in the World',
			month: 'March',
			day: '9th',
			speaker: 'Christie Hanzlik',
			imgUrl: '/christie.png',
			youtube: 'https://youtu.be/M-A7I2O3vx4',
			desc: 'Christie holds a Doctorate in History of Education from Univ, of Wisconsin. From 2013-2016, she served on the Christian Science Board of Lectureship. Her passion is working as a Practitioner at summer camp. She is on the Board of the Campership Fund. Read Christie’s many articles at JSH Online'
		},
		{
			title: 'Authentic Connections',
			month: 'May',
			day: '4th',
			speaker: 'Michael Brown',
			imgUrl: '/michael.png',
			youtube: 'https://youtu.be/U6B3w7r3bCQ',
			desc: 'Michael holds a Master of Divinity from Boston Univ. He was a US Navy Chaplain before joining Adventure Unlimited. With more than a decade in military leadership and spiritual shepherding, Michael offers a unique mixture of masterful communication and mentorship.'
		},
		{
			title: 'Breaking Barriers with Faith',
			month: 'August',
			day: '3rd',
			speaker: 'Piper Foster Wilder',
			imgUrl: '/piper.png',
			youtube: null,
			desc: 'Piper’s company develops software to maintain fleets of distributed energy resources — from microgrids to fleets of commercial and industrial solar, to energy storage assets. In 2023, she became a Dept. of Energy Awardee in the Entrepreneurship category. Read her articles on JSH Online including her Sentinel Watches on Aug 19, 2019 and Mar 28, 2022.'
		},
		{
			title: 'Let Inspiration Guide You',
			month: 'October',
			day: '5th',
			speaker: 'James Orlet',
			imgUrl: '/james.png',
			youtube: null,
			desc: 'James is a graduate of Florida State Univ. He joined A/U in 2007 and spent 4 years as an NLC Leader. He holds a Master’s Degree in Experiential Education from Minnesota State and Univ. of Colo. The “Link School” offers students interested in Christian Science, experiential high school college-prep academics, service opportunities, individual projects, and wilderness experiences.'
		},
		{
			title: 'Live Your Authentic Brilliance',
			month: 'November',
			day: '9th',
			speaker: 'Travis Thomas',
			imgUrl: '/travis.png',
			youtube: null,
			desc: 'Travis Thomas is a leadership and mindset coach who works with professional athletes and business leaders to be the best versions of themselves. He has a background in improvi- sational comedy which has allowed him to live his spirituality bigger and more authentically. His second book, “Confidence is Over- rated” is available on Amazon. You can find out more about Travis at his website www.LiveYesAnd.com'
		}
	];
	const glass = {
		background: 'rgba(255, 255, 255, 0.36)',
		borderRadius: '16px',
		boxShadow: '0 4px 30px rgba(0, 0, 0, 0.1)',
		backdropFilter: 'blur(8.7px)',
		WebkitBackdropFilter: 'blur(8.7px)'
	};
</script>

<div
	class="relative bg-[url(/mountain_lake.jpg)] bg-cover bg-fixed bg-center bg-no-repeat bg-origin-content"
>
	<div class="flex flex-col items-center gap-2 p-1">
		<h1
			class="bg-bubble shadow-big-bubble m-2 w-fit rounded-4xl pr-5 pl-5 text-center text-4xl font-bold text-wrap text-slate-700 transition-all hover:translate-x-2 hover:translate-y-1 hover:border-2 hover:border-slate-700 hover:shadow-none"
		>
			Teen Talks <br />Series
		</h1>
		<p class="text-center text-xl italic">
			A free workshop series open to all Christian Scientsts and friends, aged 13 to 19.
		</p>
	</div>

	<hr class="border-slate-700" />

	{#each lectures as lecture}
		<div
			style={glass}
			class="m-2 grid grid-cols-4 items-center justify-around rounded-3xl  p-2 md:justify-items-stretch bg-white/36 shadow-2xl backdrop-blur-[8.7px]"
		>
			{#if lecture.youtube != null}
				<a href={lecture.youtube} class="place-content-center md:justify-self-center-safe">
					<div
						class="text-s bg-mint-300 shadow-bubble flex aspect-square h-22 w-22 flex-col place-content-center items-center rounded-full text-center transition-all hover:translate-x-0.5 hover:translate-y-0.5 hover:border hover:border-slate-700 hover:shadow-none"
					>
						Sunday<br />
						{lecture.month}<br />
						{lecture.day}
					</div>
				</a>
			{:else}
				<div
					class="text-s bg-mint-300 shadow-bubble flex aspect-square h-22 w-22 flex-col place-content-center items-center rounded-full text-center transition-all hover:translate-x-0.5 hover:translate-y-0.5 hover:border hover:border-slate-700 hover:shadow-none md:justify-self-center-safe"
				>
					Sunday<br />
					{lecture.month}<br />
					{lecture.day}
				</div>
			{/if}
			<div class="col-span-2 m-1 flex flex-col justify-around wrap-normal">
				<span class="text-center font-bold text-wrap">{lecture.title}</span>
				<Dialog.Root>
					<Dialog.Trigger class="italic underline">{lecture.speaker}</Dialog.Trigger>
					<Dialog.Content>
						<Dialog.Header class="text-center text-2xl font-bold">{lecture.speaker}</Dialog.Header>
						<span>{lecture.desc}</span>
					</Dialog.Content>
				</Dialog.Root>
			</div>
			<div class="grid-shrink-0 justify-self-end-safe md:justify-self-center-safe">
				<img
					alt={lecture.speaker}
					src={lecture.imgUrl}
					class="aspect-square h-24 w-24 object-cover"
				/>
			</div>
		</div>
	{/each}

	<div class="m-3 flex flex-row justify-center">
		<Dialog.Root>
			<Dialog.Trigger
				class="bg-bubble shadow-big-bubble m-2 w-fit rounded-4xl p-2 pr-5 pl-5 text-center text-4xl font-bold text-wrap text-slate-700 transition-all active:translate-x-2 active:translate-y-1 active:border-2 active:border-slate-700 active:shadow-none"
				>Registration</Dialog.Trigger
			>
			<Dialog.Content class="bg-cream sm:max-w-[425px]">
				<Dialog.Header>
					<Dialog.Title>Registration</Dialog.Title>
					<Dialog.Description>
						Please provide the following information. Zoom information will be provided via email.
					</Dialog.Description>
				</Dialog.Header>
				<form method="POST">
					<div class="grid gap-4 py-4">
						<div class="grid grid-cols-4 items-center gap-4">
							<Label for="fname" class="text-left">First Name</Label>
							<Input id="fname" value="" class="bg-cream col-span-3" />
						</div>
						<div class="grid grid-cols-4 items-center gap-4">
							<Label for="email" class="text-left">Email</Label>
							<Input id="email" value="" type="email" class="bg-cream col-span-3" />
						</div>
						<div class="grid grid-cols-4 items-center gap-4">
							<Label for="state" class="text-left">Your state</Label>
							<Input id="state" value="" class="bg-cream col-span-3" />
						</div>
						<div class="grid grid-cols-4 items-center gap-4">
							<Label for="city" class="text-left">Your city</Label>
							<Input id="city" value="" class="bg-cream col-span-3" />
						</div>
						<div class="grid grid-cols-4 items-center gap-4">
							<Label for="grade" class="text-left">Grade in school</Label>
							<Input id="grade" value="" type="number" class="bg-cream col-span-3" />
						</div>
						<input type="hidden" value="secret" />
					</div>
					<button
						class="bg-cream shadow-bubble m-2 w-fit rounded-4xl border-1 border-slate-700 p-2 pr-5 pl-5 text-center text-4xl font-bold text-wrap text-slate-700 transition-all active:translate-x-2 active:translate-y-1 active:border-2 active:shadow-none"
						>Submit</button
					>
				</form>
			</Dialog.Content>
		</Dialog.Root>
	</div>

	<hr class="m-2 border-slate-700" />
	<a href="https://www.christiansciencenb.org" class="text-center underline"
		>The First Church of Christ, Scientist, in Newport Beach, California</a
	>
</div>
