<template>
    <div id="app">
        <app-header></app-header>
        <canvas id="myChart" height="500"></canvas>
    </div>
</template>

<script>
import { Parse } from 'parse';
import { Chart } from 'chart.js';
export default {
  name: 'app',
  data () {
    return {

    }
  },
  mounted: function(){

		var appId = '3UcdGlEEQdOfC27ogh306Zaz3NDm2nAROFtOtGME';
		Parse.initialize(appId);
		Parse.serverURL = 'https://parseapi.back4app.com';
		var jsKey = 'sptkCEzbMrfVQ92E5oTnztZWeWBdLCprr7axOS59';
		Parse.javaScriptKey = jsKey;
		var parseClass = Parse.Object.extend("Shirt");
		var query = new Parse.Query(parseClass);
		query.find({
		  success: function(results) {
		    console.log("Successfully retrieved " + results.length + " towers.");
		    var data = {};
		    data['datasets'] = [];
		    var dataPoints = [];
		    var monthlyData = {};

		    for(var i=0;i<results.length;i++){
				if(!monthlyData[results[i].attributes.date.getMonth()]) {monthlyData[results[i].attributes.date.getMonth()] = 0;}
				monthlyData[results[i].attributes.date.getMonth()] += Number.parseInt(results[i].attributes.price);
		    }
			for(var k in monthlyData){
				dataPoints.push({
		    		x: k,
		    		y: monthlyData[k]
		    	});
			}

		    data['datasets'].push({data:[monthlyData["4"], monthlyData["5"]]});
		    data.labels = ["may", "june"];

		    // initialize the chart
		    var ctx = $("#myChart");
		    var myLineChart = new Chart(ctx, {
			    type: 'bar',
			    data: data,
			    options: {
					scales: {
						yAxes: [{
							ticks: {
								beginAtZero:true
							}
						}]
					}
			    }
			});
		  },
		  error: function(error) {
		    console.log("Error: " + error.code + " " + error.message);
		  }
		});

	}
}


</script>

<style lang="scss">

</style>
