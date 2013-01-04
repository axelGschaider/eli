eli
===

in short: an interactive renamer for properties of vcf files. This is the little brother of https://github.com/axelGschaider/nucky and will always be merged into it.

THIS NEEDS TO BE PRETTY PRINTED . . .  but not today
====================================================

this is what eli works like. Renames properties in vcf files. Works on folders.

eli [folder]

[0] tells you that you can exit with Control-D (OK -> )
[1] asks for name of existing property A 
[2] A doesn't exist? -> Message -> goto [1]
[3] asks for second name B
[4] B does exist? Go on? (y/n): n -> goto[1]
[5] An occurence of B will be overwritten? Go on? (y/n/s): n -> goto[1]; s -> skipp that one
[6] renames all occurrences of A-properties to B
[7] prints out number of modified files
[8] goto [1]

for cronjobs:
nucky -i nameA nameB [folder]
Does one run of the above. Stops at questions and messages. Exits 0 at [2], 6 at [4] and 7 at [5].
Switches:
-y answer y at [4]
-Y answer y at [4] and [5]
-s answer s at 5
-g "graceful": exits 0 at [4] and [5]
Prints number of modified files (and nothing else) to stdout. No matter what.
Messages and Warnings to errout. No matter what.
