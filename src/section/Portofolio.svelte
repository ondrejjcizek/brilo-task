<script lang="ts">
	//

	import Card from '../components/Card.svelte';
	import CardWrapper from '../components/CardWrapper.svelte';
	import Container from '../components/Container.svelte';
	import Section from '../components/Section.svelte';
	import Title from '../components/Title.svelte';
</script>

<Section appended>
	<Container>
		<Title tag="h2" size="sm" uppercase>What I did</Title>
		<CardWrapper>
			<Card
				link="#todo"
				title="Epic Project"
				text="Awesome project I did in 2018. It was big experience for me."
				imageSrc="images/project-first"
				imageAlt="First Project"
			/>
			<Card
				link="#todo"
				title="Another work I did"
				text="Awesome project I did in 2018. It was big experience for me."
				imageSrc="images/project-second"
				imageAlt="Second Project"
			/>
			<Card
				link="#todo"
				title="Rebrand of this company"
				text="Awesome project I did in 2018. It was big experience for me."
				imageSrc="images/project-third"
				imageAlt="Third Project"
			/>
		</CardWrapper>
	</Container>
</Section>
