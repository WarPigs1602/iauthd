# qwebirc patch from Andreas Pschorn<br>
When your server doesn't support python2 and it's no package available, then can you use the java iauthd [mIAuthd](https://github.com/WarPigs1602/mIAuthd)<br>
<br>
[snircd](https://github.com/quakenet/snircd) needs for [qwebirc](https://github.com/qwebirc/qwebirc) the iauth-fix-webirc.patch file,<br>
Go to the snircd sources directory, and enter<br>
"wget https://raw.githubusercontent.com/WarPigs1602/snircd-patches/main/iauth-fix-webirc.patch",<br>
then enter "git apply iauth-fix-webirc.patch" to fix the IAuth crash bug and add the webchat feature,<br>
then enter "wget https://raw.githubusercontent.com/WarPigs1602/snircd-patches/main/configure.patch",
then enter "git apply configure.patch" to fix the MAXCONNECTIONS issue.
After that then enter "./configure", then "make" and "make install",<br>
and the ircd will now working with the Patch.<br>
Further configuration in the "ircd.conf" is needed or modified to:<br>
<br>
IAuth {<br>
 program = "/usr/bin/env" "python2" "path to quakenet-iauthd-file";<br>
};<br>
<br>
And set in the features section:<br>
<br>
"HIS_STATS_IAUTH" = "TRUE";<br>
<br>
Have fun for the using of this script :)
