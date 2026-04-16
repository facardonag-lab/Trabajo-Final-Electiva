<script lang="ts">
	import type { Character } from '$lib/entities/character/types';

	export let characters: Character[] = [];
</script>

{#if characters.length === 0}
	<p class="empty">No hay resultados para ese filtro.</p>
{:else}
	<div class="grid">
		{#each characters as character}
			<article class="card">
				<img src={character.image} alt={character.name} loading="lazy" />
				<div class="content">
					<h2>{character.name}</h2>
					<p>{character.status} · {character.species}</p>
					<dl>
						<div>
							<dt>Origen</dt>
							<dd>{character.originName}</dd>
						</div>
						<div>
							<dt>Ubicación</dt>
							<dd>{character.locationName}</dd>
						</div>
					</dl>
				</div>
			</article>
		{/each}
	</div>
{/if}

<style>
	.empty {
		margin: 2rem 0 0;
		color: rgba(15, 28, 46, 0.6);
	}

	.grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
		gap: 1.5rem;
	}

	.card {
		aspect-ratio: 1;
		border-radius: 50%;
		overflow: hidden;
		border: 1px solid rgba(0, 0, 0, 0.08);
		background: rgba(255, 255, 255, 0.92);
		box-shadow: 0 18px 40px rgba(37, 99, 235, 0.18);
		padding: 1.35rem;
		display: grid;
		place-items: center;
		text-align: center;
	}

	img {
		display: block;
		width: 96px;
		height: 96px;
		border-radius: 50%;
		object-fit: cover;
		border: 4px solid rgba(96, 165, 250, 0.35);
		box-shadow: 0 10px 24px rgba(37, 99, 235, 0.18);
	}

	.content {
		display: grid;
		gap: 0.55rem;
		justify-items: center;
		max-width: 78%;
	}

	h2 {
		margin: 0 0 0.35rem;
		font-size: 0.96rem;
		line-height: 1.2;
		overflow-wrap: anywhere;
	}

	p {
		margin: 0 0 0.35rem;
		color: rgba(15, 28, 46, 0.6);
		font-size: 0.88rem;
		line-height: 1.2;
		overflow-wrap: anywhere;
	}

	dl {
		margin: 0;
		display: grid;
		gap: 0.45rem;
		justify-items: center;
		width: 100%;
	}

	dt {
		font-size: 0.68rem;
		text-transform: uppercase;
		letter-spacing: 0.08em;
		color: rgba(15, 28, 46, 0.4);
	}

	dd {
		margin: 0.2rem 0 0;
		font-size: 0.82rem;
		line-height: 1.15;
		overflow-wrap: anywhere;
	}
</style>
