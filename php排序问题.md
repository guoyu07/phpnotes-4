#PHP排序
1. 冒泡排序
```php
 $arr=array(0,12,2,3,43,5,6,7,8,9);   
   //从大到小
    for($i=0;$i<count($arr)-1-$i;$i++){
           for($j=0;$j<count($arr)-1;$j++){
                if($arr[$j]<$arr[$j+1]){
                    $tem=$arr[$j];
                    $arr[$j]=$arr[$j+1];
                    $arr[$j+1]=$tem;
                }
            }
    }
    print_r($arr);
```


2.快速排序
```php
    $arr=array(10,12,2,3,43,8,96,17,8,9);   
   //从大到小
    function qsort($arr)
    {
       if( ! is_array($arr) || empty($arr)){
              return $arr;
       }  
       $len = count($arr);  
       if($len<=1){
               return $arr;
       }
       $left=array();
       $right=array();
       $key[0]=$arr[0];
       for($i=1;$i<$len;$i++){
            if($arr[$i]<$key[0]){
                $left[]=$arr[$i];
            }else{
                $right[]=$arr[$i];
            }
        }    
        $left=qsort($left);
        $right=qsort($right);    
        return array_merge($left,$key,$right);
    }
    print_r(qsort($arr));
```
