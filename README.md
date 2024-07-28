# qwebirc patch from Andreas Pschorn<br>
snircd needs for qwebirc the iauth-fix-webirc.patch file,<br>
Go to the snircd sources directory, and enter<br>
"wget https://raw.githubusercontent.com/WarPigs1602/snircd-patches/main/iauth-fix-webirc.patch",<br>
then enter "git apply iauth-fix-webirc.patch"<br>
After that then enter "./configure", "make" and "make install",<br>
and the ircd will now working with the Patch.<br>
Further configuration in the "ircd.conf" is needed or modified to:<br>
<br>
IAuth {<br>
 program = "/usr/bin/env" "python2" "<path to quakenet-iauthd-file>";<br>
};<br>
<br>
And set in the features section:<br>
<br>
"HIS_STATS_IAUTH" = "TRUE";<br>
<br>
Have fun for the using of this script :)
