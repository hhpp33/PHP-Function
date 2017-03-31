# -PHP-
## 这些PHP函数你应该惠存，以备不时之需

* PHP加密/解密  使用的是base64和md5

```php
// TODO PHP加密/解密  使用的是base64和md5
function encryptDecrypt($key, $string, $decrypt){ 
  if($decrypt){ 
    $decrypted = rtrim(mcrypt_decrypt(MCRYPT_RIJNDAEL_256, md5($key), base64_decode($string), MCRYPT_MODE_CBC, md5(md5($key))), "12"); 
    return $decrypted; 
  }else{ 
    $encrypted = base64_encode(mcrypt_encrypt(MCRYPT_RIJNDAEL_256, md5($key), $string, MCRYPT_MODE_CBC, md5(md5($key)))); 
    return $encrypted; 
  } 
}
```

* 生成随机字符串
* 得到文件扩展名
* 把获取的文件大小结果进行格式化
* 替换标签
* 获取文件目录列表
* 获取当前页面的URL
* 下载文件
* 获取用户IP
* 检测参数是否有SQL注入的可能性
