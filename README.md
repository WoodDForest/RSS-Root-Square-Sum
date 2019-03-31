# RSS-Root-Square-Sum
===
基于原生JS-求数字的平方根之和
-------------------------
##项目代码<br>
    //任何数都是由其他数的平方根之和构成，例：
    // 4=2(2);
    // 10=3(2)+1(2);

    var arrs=[];
    function gata(num,num1){
        if(!num1)num1=num; //如果第二个参数没有，第一个参数赋值给第二个参数
        if(num<1){ //如果数值小于1，说明被整除完
            arrs.sort(function(a,b){ //由大到小排序
                return b-a;
            });
            return; //处理完成
        }
        var s=Math.sqrt(num1);  //给赋值的数值开平方根
        if(s===parseInt(s)){  //判断得出的数值和整数是否相同
            arrs.push(parseInt(s));  //满足条件，直接放进数组
            num=num-s*s;  //用当前数值减去开平方前的值
            gata(num,num);  //递归(重新执行gata函数)
        }else{   //如果开平方得到的不是整数
            num1--;  //减1
            gata(num,num1);
        }
    };

    //例
    gata(245);
    console.log(arrs);
    </script>
</body>
</html>
