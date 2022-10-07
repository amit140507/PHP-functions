# PHP-functions

## end()
The end() function is an inbuilt function in PHP and is used to find the last element of the given array.

**$timeline**
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
EX: Out of 3 array it is going to print only last one.

**$endoftimeline = end($timeline);**
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

## file_get_contents()
The file_get_contents() reads a file into a string.
EX: 
``` 
<?php
echo file_get_contents("test.txt");
?>
``` 

## file_put_contents()
Write data to a file.

This function is identical to calling fopen(), fwrite() and fclose() successively to write data to a file.
If filename does not exist, the file is created. Otherwise, the existing file is overwritten, unless the FILE_APPEND flag is set.

``` 
$filename = 'text.txt';
file_put_contents( $filename, $data ,FILE_APPEND);
file_put_contents( $filename, print_r($jsonString, true),FILE_APPEND);
``` 

## fopen fwrite fclose

**fopen** — Opens file or URL.

**a+** - Open for reading and writing; place the file pointer at the end of the file. If the file does not exist, attempt to create it. In this mode,       fseek() only affects the reading position, writes are always appended.
    
``` 
<?php
$handle = fopen("c:\\folder\\resource.txt", "a+");
?>
``` 
**fwrite** — Binary-safe file write
``` 
fwrite($stream,$data,true);
``` 
**fclose** Closes an open file pointer
``` 
fclose($stream);
``` 
Ex:
``` 
$file = ABSPATH . 'coinbasetransactions.txt';
$fh = fopen($file, 'a+') ; 
fwrite($fh, print_r($jsonString, true)); 
fclose($fh); 
``` 
      
## ucwords
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

## str_replace
Replace all occurrences of the search string with the replacement string.

str_replace("$oldvalue", "$newvalue", "$varibalename");

``` 
$created_at=str_replace("T"," ","$created");
``` 
