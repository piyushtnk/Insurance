<template>
	<div class="content">
		<div class="md-layout">
			<div class="md-layout-item md-size-50 mx-auto md-small-size-100">
				<md-card class="md-card-profile">
					<div class="md-card-avatar">
						<img class="img" src="logout.webp" alt="image-preview" />
					</div>
					<md-card-content>
						<h3><md-icon class="material-icons md-size-2x"> done </md-icon>{{ logoutText }}</h3>
						<a href="/login">
							<h4><md-icon class="material-icons md-size-2x"> rotate_left </md-icon>Go To Login</h4>
						</a>
					</md-card-content>
				</md-card>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: 'Logout',
	data() {
		return {
			logoutText: 'Logging out...'
		};
	},
	mounted() {
		this.logout();
	},
	methods: {
		logout() {
			localStorage.removeItem('refreshToken');
			this.logoutText = 'Successfully logged out.';
		}
	}
};
</script>

<style lang="scss" scoped>
.mx-auto {
	margin-left: auto !important;
	margin-right: auto !important;
}

.md-card {
	margin-top: 50px;
}

.table-responsive {
	overflow: auto;
}

.table {
	width: 100%;
	max-width: 100%;
	margin-bottom: 1rem;
	background-color: transparent;

	thead tr th {
		font-size: 1.063rem;
		border-top-width: 0;
		font-weight: 300;
		border-bottom: 1px solid rgba(0, 0, 0, 0.06);
	}

	& > tbody > tr > td,
	& > tbody > tr > th,
	& > tfoot > tr > td,
	& > tfoot > tr > th,
	& > thead > tr > td,
	& > thead > tr > th {
		padding: 12px 8px;
		vertical-align: middle;
	}

	& > tbody > tr {
		position: relative;
	}

	td,
	th {
		padding: 0.75rem;
		vertical-align: top;
		border-top: 1px solid rgba(0, 0, 0, 0.06);
	}
}
</style>
