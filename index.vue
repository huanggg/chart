option = {
    tooltip: { //鼠标悬停提示内容
                    trigger: 'axis',
                    axisPointer: {            // 坐标轴指示器，坐标轴触发有效
                        type: 'cross'    // 十字线显示
                    }
                },
                legend: {
                    y: '20px',
                    data: ['标准保费', '增长'],
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
                     data: [1, 2, 3, 4, 5, 6],
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
                        itemStyle: {normal: {color: '#2d91ff', label: {show: true}}},
                        data: [100,200, 30, 90,210,110]
                    },
                       //第二个柱状图的数据
                 {
                        name: '承保',
                        type: 'line',
                        xAxisIndex: 1, //第二个柱状图的数据
                        itemStyle: {
                            normal: {
                                color: '#d5e9ff',
                                label: {
                                    show: true, formatter: function (p) {
                                        return p.value > 0 ? (p.value + '\n') : '';
                                    }
                                }
                            }
                        },
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
                        itemStyle: {
                            normal: {
                                color: '#ffb348',
                                label: {
                                    show: true,
                                    formatter: '{c}%',
                                    textStyle: {
                                        color: '#000000'
                                    }
                                }
                            }
                        },
                        data: [3, 9, 2, 5, 7, 10]
                    },
                ]
};
