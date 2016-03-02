#cURL常用的几个PHP函数
`curl`

- - -

- ###使用cURL来GET数据
```php
  function getCURL($url){
        $curl = curl_init();
        curl_setopt($curl, CURLOPT_URL, $url);
        curl_setopt($curl, CURLOPT_HEADER, 0);
        curl_setopt($curl, CURLOPT_TIMEOUT, 3);     //超时时间
        curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
        $data = curl_exec($curl);
        curl_close($curl);
        return $data;
    }
```
- ###使用cURL来POST数据
```php
 function _curl_post($url, $vars)
    {
        $ch = curl_init();
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch, CURLOPT_POST, 1);
        curl_setopt($ch, CURLOPT_POSTFIELDS, $vars);
        $data = curl_exec($ch);
        curl_close($ch);
        if ($data) {
            return $data;
        } else {
            return false;
        }
    }
```

- ###使用cURL,需要HTTP服务器认证
```php
function _curl_post($url, $vars)
{
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
    curl_setopt($ch, CURLOPT_URL, $url);
    curl_setopt($ch, CURLOPT_POST, 1);
    curl_setopt($ch, CURLOPT_POSTFIELDS, $vars);
    $data = curl_exec($ch);
    curl_close($ch);
    if ($data) {
        return $data;
    } else {
        return false;
    }
}
```
- ###给cURL加个代理服务器
```php
 $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, ‘http://js8.in‘);
    curl_setopt($ch, CURLOPT_HEADER, 1);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
    curl_setopt($ch, CURLOPT_HTTPPROXYTUNNEL, 1);
    curl_setopt($ch, CURLOPT_PROXY, ‘代理服务器地址（js8.in）:端口’);
    curl_setopt($ch, CURLOPT_PROXYUSERPWD, ‘代理用户:密码’);
    $data = curl_exec();
    curl_close($ch);
```













