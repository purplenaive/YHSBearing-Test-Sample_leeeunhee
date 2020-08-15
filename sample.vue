<!-- HTML 시작 !-->
<div id="app">
	<v-app id="inspire">

    <v-container fluid>

        <v-layout class="top_time">
            <v-flex class="top_time__inner">
                <span class="time">2020-03-14 12:00:00</span>
            </v-flex>
        </v-layout>

        <v-layout class="flex_temp">

            <template v-for="item in machine">
                    <v-col :key="item.idx" class="temp__item">
                        <v-row class="temp__top">
                            <p class="f_mname">{{item.mid}}</p>
                            <p class="f_p">{{item.process}}</p>
                        </v-row>
                        <v-row class="temp__center">
                            <span class="f_end">{{item.timer}}</span>
                        </v-row>
                        <v-row class="temp__percent">
                            <v-progress-linear value="15" height="5vw" color="#FFC107" background-color="#F3E1A9">
                                <p class="vt vt__count">{{ item.count}}</p> 
                                <p class="vt vt__time">{{ item.fTime }}</p>
                            </v-progress-linear>
                        </v-row>
                    </v-col>
            </template>

        </v-layout>

        
    </v-container>

	</v-app>
</div>
<!-- HTML 끝 !-->

<style>
<!-- CSS 시작 !-->
@font-face {
    font-family: 'GmarketSansMedium';
    src: url('https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_2001@1.1/GmarketSansMedium.woff') format('woff');
    font-weight: normal;
    font-style: normal;
}
@font-face {
    font-family: 'GmarketSansBold';
    src: url('https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_2001@1.1/GmarketSansBold.woff') format('woff');
    font-weight: normal;
    font-style: normal;
}
div, p, span {
    line-height: 1.1;
}

/* 컨테이너 */
.container {
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-content: stretch;
    padding: 0;
}

/* 최상단 날짜 시간 표시 */
.top_time {
    flex: 0 0 auto;
    justify-content: center;
    align-items: center;
    background: #444444;
}
.top_time__inner {
    text-align: center;
}
.time{
	color: #FFC107;
    text-align: center;
    font-family: 'GmarketSansMedium',Roboto, sans-serif;
}

/* template item */
.flex_temp {
	flex-wrap: wrap;
	justify-content: space-between;
	align-content: stretch;
}
.temp__item {
    width: 33.333%;
    display: flex;
    flex-direction: column;
    flex: 1 1 auto;
    align-items: stretch;
    box-sizing: border-box;
    border-bottom: 3px solid #444444;
    border-right: 3px solid #444444;
    padding: 0;
    position: relative;
}
.temp__item:nth-child(3n+1) {
    border-left: 3px solid #444444;
}
.temp__item .row {
    margin: 0;
}

/* 템플릿 상단 */
.temp__top {
    flex-direction: column;
    justify-content:center;
    align-items: center;
    flex: 1 1 0;
    background: #cccccc;
}
.temp__top > p {
    width: 100%;
    flex: 0 1 auto;
    margin: 0;
    text-align: center;
}
.f_mname {
    font-family: 'GmarketSansBold',Roboto, sans-serif;
    font-weight: bold;
}
.f_p {
    font-family: 'GmarketSansMedium',Roboto, sans-serif;
    word-break: keep-all;
}

/* 템플릿 중앙 */
.temp__center {
    flex: 8 8 auto;
    justify-content: center;
    align-items: center;
}
.f_end {
    font-family: 'GmarketSansBold',Roboto, sans-serif;
    text-align: center;
}

/* 템플릿 하단 수치 */
.temp__percent {
    flex: 1 1 0;
    background: white;
}
.temp__percent .v-progress-linear__content {
    align-items: center;
}
.temp__percent .vt {
    font-family: 'GmarketSansMedium',Roboto, sans-serif;
    margin: 0;
}
.vt__count {
    padding-left: 1.25vw;
}
.vt__time {
    padding-right: 1.25vw;
}

/* 화면 크기 가로 > 세로 */
@media all and (orientation: landscape) {
    /* 최상단 날짜 시간 표시 */
    .top_time__inner {
        padding: 1vw 0;
    }
    .time {
        font-size: 2.5vw;
    }

    /* 템플릿 상단 */
    .temp__top {
        padding: 0.8vw 0 0.6vw;
    }
    .f_mname {
        font-size: 1.7vw;
        padding-bottom: 0.5vw;
    }
    .f_p {
        font-size: 1.3vw;
    }
    /* 템플릿 중앙 */
    .f_end {
        font-size: 5.5vw;
    }

    /* 템플릿 하단 수치 */
    .temp__percent .v-progress-linear__content {
        justify-content: space-between;
    }
    .temp__percent .vt {
        font-size: 1.5vw;
    }
}

/* 화면 크기 가로 < 세로 */
@media all and (orientation: portrait) { 
    /* 최상단 날짜 시간 표시 */
    .top_time__inner {
        padding: 2vw 0;
    }
    .time {
        font-size: 4.3vw;
    }

    /* 템플릿 상단 */
    .temp__top {
        padding: 1.2vw 0 1vw;
    }
    .f_mname {
        font-size: 2.8vw;
        padding-bottom: 1.5vw;
    }
    .f_p {
        font-size: 2vw;
    }
    /* 템플릿 중앙 */
    .f_end {
        font-size: 5.7vw;
    }

    /* 템플릿 하단 수치 */
    .temp__percent .v-progress-linear {
        height: 13vw !important; 
    }
    .temp__percent .v-progress-linear__content {
        flex-direction: column;
        justify-content: center;
    }
    .temp__percent .vt {
        width: 100%;
        font-size: 3vw;
        padding: 0;
        text-align: center;
    }
}

/* 예외 세로 디바이스 */
@media all and (max-width: 400px) and (orientation: portrait) {
    /* 템플릿 상단 */
    .f_p {
        word-break: break-word;
    }
}

<!-- CSS 끝 !-->
</style>

<script>
<!-- JS 시작 !-->
new Vue({
	  el: '#app',
	  vuetify: new Vuetify(),
	  data () {
	    return {
	      tab: null,
	      machine: [
	        {
	          mid : 'Puma280',
	          idx : 1,
	          process : 'CS98D25H49-01-2',
	          timer : '가공완료',
	          count : '100/100',
	          fTime : '0 시간 6 분',
	          
	        },
	        {
	          mid : 'PumaV400',
	          idx : 2,
	          process : 'O0229',
	          timer : '04:34',
	          count : '4/100',
	          fTime : '84 시간 40 분',
	          
	        },
	        {
	          mid : 'Lynx220C',
	          idx : 3,
	          process : 'D580007-02-F',
	          timer : '01:33',
	          count : '459/500',
	          fTime : '2 시간 36 분',
	          
	        },
	        {
	          mid : 'Puma240',
	          idx : 4,
	          process : 'WGR150D35H24-02-1',
	          timer : '00:10',
	          count : '70/100',
	          fTime : '1 시간 31 분',
	          
	        },
	        {
	          mid : 'Lynx220CL',
	          idx : 5,
	          process : 'CS98D25H49-02-02',
	          timer : '02:34',
	          count : '12/100',
	          fTime : '5 시간 0 분',
	          
	        },
	        {
	          mid : 'Lynx220SY',
	          idx : 6,
	          process : 'JIG-CD',
	          timer : 'READY',
	          count : '110/200',
	          fTime : '23 시간 48 분',
	          
	        },
	      ],
	    }
	  },
	})
<!-- JS 끝 !-->
</script>