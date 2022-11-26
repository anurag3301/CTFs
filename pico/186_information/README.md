first just look run strings on the image with size more than 20 character, and you get this
```sh
strings -n 20 cat.jpg
```
```
http://ns.adobe.com/xap/1.0/
' id='W5M0MpCehiHzreSzNTczkc9d'?>
<x:xmpmeta xmlns:x='adobe:ns:meta/' x:xmptk='Image::ExifTool 10.80'>
<rdf:RDF xmlns:rdf='http://www.w3.org/1999/02/22-rdf-syntax-ns#'>
 <rdf:Description rdf:about=''
  xmlns:cc='http://creativecommons.org/ns#'>
  <cc:license rdf:resource='cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9'/>
 <rdf:Description rdf:about=''
  xmlns:dc='http://purl.org/dc/elements/1.1/'>
    <rdf:li xml:lang='x-default'>PicoCTF</rdf:li>
```
Here we see two interesting character sequence which are
+ `W5M0MpCehiHzreSzNTczkc9d`
+ `cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9`

They seem to be base64 encoded, lets try to decode them
```sh
echo "W5M0MpCehiHzreSzNTczkc9d" | base64 --decode
```
Running this got us `[42!573]` which doesnt seem to be the flag, lets try on second one

```sh
echo "cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9" | base64 --decode
```
And the output `picoCTF{the_m3tadata_1s_modified}` does seem like the flag
