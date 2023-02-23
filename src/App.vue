<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template id="app">
	<nav>
		<div id="user" class="d-flex">
			<button
				class="akk-och btn btn-primary"
				data-bs-toggle="modal"
				type="button"
				data-bs-target="#staticBackdrop"
			>
				<span>Fall name</span>
			</button>
			<p class="full">{{ fullName }}</p>
		</div>
		<a href="">
			<h1 style="font-size: 60px">
				I<span style="color: darkgoldenrod">N</span>
			</h1>
		</a>
		<div class="router">
			<RouterLink to="/">Maktab kitoblar</RouterLink>
			<RouterLink to="/about">Badiy kitoblar</RouterLink>
			<RouterLink to="/section">Jurnallar</RouterLink>
		</div>
	</nav>
	<!-- Modal -->
	<div
		class="modal fade"
		id="staticBackdrop"
		data-bs-backdrop="static"
		data-bs-keyboard="false"
		tabindex="-1"
		aria-labelledby="staticBackdropLabel"
		aria-hidden="true"
	>
		<div class="modal-dialog">
			<div class="modal-content">
				<div class="modal-header">
					<h1 class="modal-title fs-5" id="staticBackdropLabel">user</h1>
					<button
						type="button"
						class="btn-close"
						data-bs-dismiss="modal"
						aria-label="Close"
					></button>
				</div>
				<div class="modal-body">
					<div class="akk">
						<p>
							<label for="lastName">Last name</label>
							<input type="text" id="lastName" v-model="lastName" />
						</p>
						<p>
							<label for="firstName">First name</label>
							<input type="text" id="firstName" v-model="firstName" />
						</p>
					</div>
				</div>
				<div class="modal-footer">
					<button type="button" class="btn btn-primary" data-bs-dismiss="modal">
						Ok
					</button>
				</div>
			</div>
		</div>
	</div>
	<div class="router-about">
		<RouterView />
	</div>
</template>

<style>
* {
	margin: 0;
	box-sizing: border-box;
}
nav {
	width: 100%;
	height: 100px;
	display: flex;
	justify-content: space-between;
	padding: 0 20px;
	align-items: center;
	position: fixed;
	background-color: black;
	opacity: 0.8;
	z-index: 1;
	top: 0;
	left: 0;
}

.router-about {
	margin-top: 100px;
	width: 100%;
}

.full {
	margin-left: 15px;
	font-size: 20px;
	color: antiquewhite;
}

.router {
	font-size: 18px;
}
.router a.router-link-exact-active {
	color: var(--color-text);
}
.router a.router-link-exact-active:hover {
	background-color: transparent;
}
.router a {
	display: inline-block;
	padding: 0 1rem;
	border-left: 1px solid var(--color-border);
}

.router a:first-of-type {
	border: 0;
}
</style>
<script>
export default {
	data() {
		return {
			fathersName: "",
			firstName: "",
			lastName: "",
		};
	},
	computed: {
		fullName() {
			return this.lastName + " " + this.firstName;
		},
	},
};
</script>
