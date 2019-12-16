option = {
   tooltip : {
show : true,
trigger: 'axis',
formatter: '占用率<br/>cup: {c0}%<br />{a1}: {c1}%<br />{a2}: {c2}%<br />{a3}: {c3}%<br />{a4}: {c4}%'
},
                legend: {
                    y: '20px',
                    data: ['标准保费', '增长','承保'],
                    selectedMode: false,
                },
                xAxis: [
                    //X轴
                    {
                        type: 'category',
                        data: [1, 2, 3, 4, 5, 6],
                        axisLabel: {interval: 0},
                    },
                   //x轴显示两组数据  第2个X轴
                     {
                        type: 'category',
                       axisLine: {show: false},
                        axisTick: {show: false},
                        axisLabel: {show: false, interval: 0},
                       splitArea: {show: false},
                      splitLine: {show: false},
                   
                    }
                ],
                yAxis: [ //两个y轴  左边y轴
                 //右边y轴
                    {
                        type: 'value',
                        name: "增长",
                        axisLabel: {
                            show: true,
                            interval: 'auto',
                            formatter: '{value} %'
                        },
                        splitNumber: 10,
                        splitLine: {
                            show: true,
                            lineStyle: {
                                type: 'dashed'
                            }
                        },
                        splitArea: {
                            show: false
                        },
                        // max: 100,
                        // interval: 10,
                    },
                    {
                        type: 'value',
                        name: "金额(元)",

                        axisLabel: {
                            show: true,
                            interval: 'auto',
                            formatter: '{value} '
                        },
                        splitNumber: 10,
                        splitLine: {
                            show: true,
                            lineStyle: {
                                type: 'dashed'
                            }
                        },
                        // splitArea: {
                        //     show: false
                        // },
                        // max: 100,
                        // interval: 10,
                    },
                   
                ],
                series: [ //用于指定图标显示类型
                 //第一个柱状图的数据
                    {
                        name: '标准保费',
                        type: 'line',
                        yAxisIndex: '0',// 第一个柱状图的数据
                      
                        data: [100,200, 30, 90,210,110]
                    },
                       //第二个柱状图的数据
                 {
                        name: '承保',
                        type: 'line',
                    
                       
                        data: [120, 300, 100, 170, 300,200]
                    },
                   
                    {
                        name: '增长',
                        type: 'line',
                        symbol: 'emptyCircle',
                        showAllSymbol: true, //动画效果
                        symbolSize: 3,
                        smooth: true, //光滑的曲线
                        yAxisIndex: '1',      
                       
                        data: [3, 9, 2, 5, 7, 10]
                    },
                ]
