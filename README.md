# PHP-functions

## [end()](https://www.php.net/manual/en/function.end.php)
The end() function is an inbuilt function in PHP and is used to find the last element of the given array.

#### $timeline

``` 
print_r($timeline);
``` 
#### Result:
``` 
Array
(
    [0] => Array
        (
            [time] => 2022-09-30T16:04:04Z
            [status] => NEW
        )

    [1] => Array
        (
            [time] => 2022-09-30T16:07:08Z
            [status] => PENDING
            [payment] => Array
                (
                    [value] => Array
                        (
                            [amount] => 0.00010157
                            [currency] => BTC
                        )

                    [network] => bitcoin
                    [transaction_id] => 8ebc2941b5e4695be4bc778450b273c6eea80040a1c3b1900e5182e79c9bba11
                )

        )

    [2] => Array
        (
            [time] => 2022-09-30T16:26:31Z
            [status] => UNRESOLVED
            [context] => OVERPAID
            [payment] => Array
                (
                    [value] => Array
                        (
                            [amount] => 0.00010157
                            [currency] => BTC
                        )

                    [network] => bitcoin
                    [transaction_id] => 8ebc2941b5e4695be4bc778450b273c6eea80040a1c3b1900e5182e79c9bba11
                )

        )

)
``` 

Out of 3 array it is going to print only last one.

#### $endoftimeline = end($timeline);

``` 
print_r($endoftimeline);

``` 
Result:
``` 
Array
(
    [time] => 2022-09-30T16:26:31Z
    [status] => UNRESOLVED
    [context] => OVERPAID
    [payment] => Array
        (
            [value] => Array
                (
                    [amount] => 0.00010157
                    [currency] => BTC
                )

            [network] => bitcoin
            [transaction_id] => 8ebc2941b5e4695be4bc778450b273c6eea80040a1c3b1900e5182e79c9bba11
        )

)

``` 

## [file_get_contents()](https://www.php.net/manual/en/function.file-get-contents.php)
The file_get_contents() reads a file into a string.
Ex: 
``` 
<?php
echo file_get_contents("test.txt");
?>
``` 

## [file_put_contents()](https://www.php.net/manual/en/function.file-put-contents.php)
Write data to a file.

This function is identical to calling fopen(), fwrite() and fclose() successively to write data to a file.
If filename does not exist, the file is created. Otherwise, the existing file is overwritten, unless the FILE_APPEND flag is set.

``` 
$filename = 'text.txt';
file_put_contents( $filename, $data ,FILE_APPEND);
file_put_contents( $filename, print_r($jsonString, true),FILE_APPEND);
``` 

## [fopen()](https://www.php.net/manual/en/function.fopen.php) [fwrite()](https://www.php.net/manual/en/function.fwrite.php) [fclose()](https://www.php.net/manual/en/function.fclose.php)

**fopen** — Opens file or URL.

**a+** - Open for reading and writing; place the file pointer at the end of the file. If the file does not exist, attempt to create it. In this mode,       fseek() only affects the reading position, writes are always appended.
    
``` 
<?php
$fh = fopen("$file, "a+");
?>
``` 
**fwrite** — Binary-safe file write
``` 
fwrite($fh,$data,true);
``` 
**fclose** — Closes an open file pointer
``` 
fclose($fh);
``` 
Ex:
``` 
$file = 'test.txt';
$fh = fopen($file, 'a+') ; 
fwrite($fh, print_r($jsonString, true)); 
fclose($fh); 
``` 
      
## [ucwords()](https://www.php.net/manual/en/function.ucwords.php)
Uppercase the first character of each word in a string.
``` 
<?php
$foo = 'hello world!';
$foo = ucwords($foo);             // Hello World!

$bar = 'HELLO WORLD!';
$bar = ucwords($bar);             // HELLO WORLD!
$bar = ucwords(strtolower($bar)); // Hello World!
?>
``` 

## [str_replace()](https://www.php.net/manual/en/function.str-replace.php)
Replace all occurrences of the search string with the replacement string.
``` 
str_replace("$oldvalue", "$newvalue", "$varibalename");
``` 
``` 
$created_at=str_replace("T"," ","$created");
``` 

## [filemtime()](https://www.php.net/manual/en/function.filemtime.php)
 Gets file modification time


```
<?php
// outputs e.g.  somefile.txt was last modified: December 29 2002 22:16:23.

$filename = 'somefile.txt';
if (file_exists($filename)) {
    echo "$filename was last modified: " . date ("F d Y H:i:s.", filemtime($filename));
}
?>
```
```
$style_ver = filemtime( get_stylesheet_directory() . '/assets/js/custom.js' );
    wp_register_script('allyearcooling_custom_js', get_stylesheet_directory_uri().'/assets/js/custom.js', array(), $style_ver);
```
