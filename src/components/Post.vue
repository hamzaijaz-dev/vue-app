<template>
<div class="container">
<div class="row">
    <div class="col-md-1"></div>
	<div class="col-md-6">
		<div id="postlist">
			<div class="panel">
                <div class="panel-heading">
                    <div class="text-center">
                        <div class="row">
                            <div class="col-sm-9">
                                <h3 class="pull-left">Welcome</h3>
                            </div>
                            <div class="col-sm-3">
                                <h4 class="pull-right">
                                <small><em>2014-07-30<br>18:30:00</em></small>
                                </h4>
                            </div>
                        </div>
                    </div>
                </div>

            <div class="panel-body">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
                tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
                quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
                consequat. Duis aute irure dolor in... <a href="#">Read more</a>
            </div>

            <div class="panel-footer">
              <span class="label label-default">Welcome</span>
              <span class="label label-default">Updates</span>
              <span class="label label-default">July</span>
            </div>
        </div>

    </div>
		<div class="text-center"><a href="#" id="loadmore" class="btn btn-primary">Older Posts...</a></div>
</div>
	<div class="col-md-1"></div>
	<div class="col-md-3">
	</div>
	<div class="col-md-1">
	</div>
</div>
</div>
</template>

<script>
export default {
  name: "Post"
}
</script>

<style scoped>

</style>
