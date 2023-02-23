<template>
	<div class="about">
		<button
			id="ink"
			data-bs-toggle="modal"
			type="button"
			data-bs-target="#staticBack"
		>
			<i class="bi bi-cart4"></i><span>{{ count + count1 + count2 }}</span>
		</button>
		<div
			class="modal fade"
			id="staticBack"
			data-bs-backdrop="static"
			data-bs-keyboard="false"
			tabindex="-1"
			aria-labelledby="staticBackdrop"
			aria-hidden="true"
		>
			<div class="modal-dialog">
				<div class="modal-content">
					<div class="modal-header">
						<h1 class="modal-title fs-5" id="staticBackdropLabel">
							Buyurtmalar: Badiy kitob
						</h1>
						<button
							type="button"
							class="btn-close"
							data-bs-dismiss="modal"
							aria-label="Close"
						></button>
					</div>
					<div class="modal-body">
						<h3>O'tgan kunlar: {{ count }}</h3>
						<h3>Shum bola: {{ count1 }}</h3>
						<h3>Oq kema: {{ count2 }}</h3>
					</div>
					<div class="modal-footer">
						<button
							type="button"
							class="btn btn-primary"
							data-bs-dismiss="modal"
						>
							Ok
						</button>
					</div>
				</div>
			</div>
		</div>
		<div id="qidiruv">
			<div id="app1" class="meseg">
				<h1>O'tgan kunlar</h1>
				<img
					src="https://upload.wikimedia.org/wikipedia/uz/thumb/8/81/O%CA%BBtgan_kunlar.jpg/200px-O%CA%BBtgan_kunlar.jpg"
					alt="o'tgan kunlar"
				/>
				<div class="buttons">
					<button v-on:click="minus">
						<i class="bi bi-cart-dash" style="font-size: 20px"></i>
					</button>
					<button>{{ count }}</button>
					<button v-on:click="plass">
						<i class="bi bi-cart-plus" style="font-size: 20px"></i>
					</button>
				</div>
			</div>
			<div id="app2" class="meseg">
				<h1>Shum bola</h1>
				<img
					src="https://assets.asaxiy.uz/product/items/desktop/dd63b88afdacdb31510f31ce6ac39a382020090718202360330Cy0T9OEdQL.jpg.webp"
					alt="shum bola"
				/>
				<div class="buttons">
					<button v-on:click="minus1">
						<i class="bi bi-cart-dash" style="font-size: 20px"></i>
					</button>
					<button>{{ count1 }}</button>
					<button v-on:click="plass1">
						<i class="bi bi-cart-plus" style="font-size: 20px"></i>
					</button>
				</div>
			</div>
			<div id="app2" class="meseg">
				<h1>Oq kema</h1>
				<img
					src="https://i.mycdn.me/i?r=AzEPZsRbOZEKgBhR0XGMT1RkEgUYQ6nRloej3eKbYFPoKaaKTM5SRkZCeTgDn6uOyic,https://i.mycdn.me/i?r=AzEPZsRbOZEKgBhR0XGMT1RkEgUYQ6nRloej3eKbYFPoKaaKTM5SRkZCeTgDn6uOyic"
					alt="shum bola"
				/>
				<div class="buttons">
					<button v-on:click="minus2">
						<i class="bi bi-cart-dash" style="font-size: 20px"></i>
					</button>
					<button>{{ count2 }}</button>
					<button v-on:click="plass2">
						<i class="bi bi-cart-plus" style="font-size: 20px"></i>
					</button>
				</div>
			</div>
		</div>
	</div>
</template>

<style setup>
#qidiruv {
	width: 100%;
	display: flex;
	gap: 80px;
}
#ink {
	background-color: transparent;
	position: relative;
	border: 0;
	position: fixed;
	top: 26px;
	right: 440px;
	z-index: 2;
}
#ink i {
	color: aqua;
	font-size: 28px;
}
#ink span {
	font-size: 14px;
	border-radius: 50%;
	width: 20px;
	height: 20px;
	background-color: red;
	position: absolute;
	z-index: 2;
	right: 1px;
	top: 7px;
}
.meseg {
	width: 300px;
	background-color: gray;
	box-shadow: -16px 6px 15px #ced0d3;
	border-radius: 10px;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	padding: 20px 0;
	gap: 20px;
}
.meseg button + button {
	border-left: 1px solid black;
}
.meseg button {
	border: 0;
	background-color: aquamarine;
	color: blue;
	padding: 5px 10px;
	width: 50px;
	font-size: 20px;
}
img {
	width: 100%;
	height: 350px;
	size: cover;
}
.buttons {
	display: flex;
	justify-content: center;
}
@media (max-width: 1012px) {
	#qidiruv {
		gap: 20px;
		display: flex;
		flex-wrap: wrap;
		height: 100%;
	}
	.meseg {
		width: 300px;
		margin: 0;
	}
}
</style>
<script>
export default {
	data() {
		return {
			count: 0,
			count1: 0,
			count2: 0,
		};
	},
	methods: {
		plass() {
			this.count += 1;
		},
		plass1() {
			this.count1 += 1;
		},
		plass2() {
			this.count2 += 1;
		},
		minus() {
			if (this.count > 0) {
				this.count -= 1;
			} else {
				this.count = 0;
				alert("Sizda O'tgan kunlar kitobi yo'q");
			}
		},
		minus1() {
			if (this.count1 > 0) {
				this.count1 -= 1;
			} else {
				this.count1 = 0;
				alert("Sizda Shum bola kitobi yo'q");
			}
		},
		minus2() {
			if (this.count2 > 0) {
				this.count2 -= 1;
			} else {
				this.count2 = 0;
				alert("Sizda Oq kema kitobi yo'q");
			}
		},
	},
};
</script>
