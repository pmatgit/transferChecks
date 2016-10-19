# Hints, tools to check the transfers from AliEn to nyx

To check the transferrate we get creation time and last changed time from lustre and write it to an txt file which can be used as input for a root tree.
```
find /lustre/nyx/alice/alien/alice/data/2015/LHC15o/*/pass1/AOD  -maxdepth 2 -name aod_archive.zip -exec stat --format "%n %Y %X %s"  {} \; > LHC15o_pass1_AOD.txt
sed -i '1s/^/fileName\/C:modificationTime\/D:creationTime\/D:fileSize\/D\n/' LHC15o_pass1_AOD.txt

```