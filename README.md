# PHP-functions

## end()
$endoftimeline = end($timeline);

## file_get_contents

$file = ABSPATH . 'coinbasetransactions.txt';
file_put_contents( $file, print_r($jsonString, true),FILE_APPEND);

## fopen fwrite fclose
$file = ABSPATH . 'coinbasetransactions.txt';
$fh = fopen($file, 'a+') ; 
fwrite($fh, print_r($jsonString, true)); 
fclose($fh); 
    
    
## ucwords
ucwords(strtolower($endoftimeline['status']));  


## str_replace
$created_at=str_replace("T"," ","$created");
