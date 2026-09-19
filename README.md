# blorple.py: Extract release and serial number from interactive fiction files

_Explore an object's mystic connections._

Accepts bare Z-code (.z3–.z8, etc.), Inform Glulx (.ulx), TADS 2/3 (.gam / .t3), ADRIFT .taf (3.7–5), Quest .quest packages, and Blorbs.

The serial number is a YYMMDD date. Bare ADRIFT .taf files have no release number (only serial from CompileDate / LastUpdated). TADS stories without GameInfo use the image header compile timestamp as serial only. Quest .quest packages use iFiction `releasedate` or the ZIP last-mod date of `game.aslx`.

Usage:

```
% python3 blorple.py anchor.z8
release: 5
serial: 990206
% python3 blorple.py CounterfeitMonkey.gblorb
release: 11
serial: 230220
% python3 blorple.py cain.t3
release: 6
serial: 230911
% python3 blorple.py deep.gam
release: 1
serial: 900101

# ADRIFT .taf only supports a serial number.
% python3 blorple.py Hamper.taf
serial: 030802

# Some TADS files don't contain GameInfo; serial only
% python3 blorple.py bmiss.gam
serial: 020410

# Quest .quest: iFiction releasedate, or game.aslx ZIP date
% python3 blorple.py modern.quest
release: 1
serial: 260909
% python3 blorple.py legacy.quest
serial: 260909
```
