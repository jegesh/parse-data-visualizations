<template>
  <div id="header">
      <nav class="navbar navbar-custom navbar-fixed-top" role="navigation">

        <div class="container navigation">

            <div class="navbar-header page-scroll">
                <button type="button" class="navbar-toggle" data-toggle="collapse" data-target=".navbar-main-collapse">
                    <i class="fa fa-bars"></i>
                </button>
                <a class="navbar-brand" href="index.html">
                    <img src="../assets/parse_icon.png" alt="" height="80" />
                </a>
            </div>

            <!-- Collect the nav links, forms, and other content for toggling -->
            <div class="collapse navbar-collapse navbar-right navbar-main-collapse">
			  <ul class="nav navbar-nav">
				<li class="active"><a href="#intro">Home</a></li>
				<li><a href="#service">Settings</a></li>

				<li class="dropdown">
				  <a href="#" class="dropdown-toggle" data-toggle="dropdown">More <b class="caret"></b></a>
				  <ul class="dropdown-menu">
				    <li><a href="index.html">Home CTA</a></li>
					<li><a href="index-form.html">Home Form</a></li>
					<li><a href="index-video.html">Home video</a></li>
				  </ul>
				</li>
			  </ul>
            </div>
            <!-- /.navbar-collapse -->
        </div>
        <!-- /.container -->
    </nav>
  </div>
</template>

<script>
</script>

<style lang="scss">
	.navbar-brand {
  		padding-top: 0px;
    	margin-top: 0px;
}
</style>
