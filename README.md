<div align="center">

## register\_globals workaround


</div>

### Description

since PHP version 4.2.0 you can no longer pass variables from one page to the other with a form without using the  super-global variables $_POST or $_GET.

These were introduced for security reasons, but it makes upgrading your old scripts a pain.

imagine having to go through all the files on your server, changing hundreds of variables...

with this script this problem is gone in no time.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[lixlpixel](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/lixlpixel.md)
**Level**          |Beginner
**User Rating**    |3.8 (15 globes from 4 users)
**Compatibility**  |PHP 4\.0
**Category**       |[Coding Standards](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/coding-standards__8-33.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/lixlpixel-register-globals-workaround__8-1086/archive/master.zip)





### Source Code

```
put following code
&lt;?<pre>
if ( phpversion() >="4.2.0") extract($_POST);
?>
</pre>
or if you're not sure where your variables come from
&lt;?<pre>
if ( phpversion() >= "4.2.0")
{
 extract($_POST);
 extract($_GET);
 extract($_SERVER);
 extract($_ENV);
 extract($_COOKIE);
}
?>
</pre>
on top of your old script
(or better put it in a file included in every page of your script)
and you're all set.
(sometimes life can be sooo easy)
```

