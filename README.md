# TUPU PHP SDK

SDK for TUPU visual recognition service
######  
<https://www.tuputech.com>

## Example

```
require 'tupuclient.php';

//Using remote iamge URLs
//$images = array('http://img.xxx.com/1.jpg', 'http://img.xxx.com/2.jpg');
//Upload files with local path
$images = array('@img/1.jpg', '@img/2.jpg');

//Post tags relative to images
$tags = array('room1', 'room2');
//Post a general tag relative to images
//$tags = 'room1';
//$tags = array('room1');

//NOTE: Paste the path of your private key pem file here
// generating RSA private key:
// # openssl genrsa -out rsa_private_key.pem 1024
$privateKey = file_get_contents('./your_private_key.pem');

//NOTE: Paste your Screct-ID here
// Apply for account and secret ID: https://www.tuputech.com
$secretId = 'your_secret_id';

$tupu = new TupuClient($privateKey, $secretId);

$result = $tupu->recognition($images, $tags);
var_dump($result);
```

### Method recognition
- **$images**: array of image URLs or Paths (path starts with '@')
- **$tags**: tag of image (optional); string value as general tag for all images; if count of tags is less than count of images, the last tag will be used for the rest.

## License

[MIT](http://www.opensource.org/licenses/mit-license.php)
