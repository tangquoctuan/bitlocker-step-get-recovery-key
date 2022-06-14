# bitlocker-step-recovery-key
1. Download & install `win32diskimager` https://sourceforge.net/projects/win32diskimager/.
2. Download `John the Ripper password cracker` https://www.openwall.com/john/ (1.9.0-jumbo-1 64-bit Windows binaries in).
3. Download `HashCat` https://hashcat.net/beta/.
4. Open `win32diskimager` => create image file.
5. Copy file `bitlocker2john.exe` and `cygwin1.dll` from `John the Ripper password cracker` to parent dir.
6. From current dir, on explorer type `cmd` => `bitlocker2john.exe -i {{image}}`. After run success, get haskey 
![Screenshot 2022-06-14 230522](https://user-images.githubusercontent.com/19494121/173624094-cf69605b-2a29-4441-944d-1e356c2b503f.png)
7. Create file `Hash.txt` store ` User Password with MAC verification (slower solution, no false positives)`
8. Copy `Hash.txt` to HashCat program dir.
9. In `Hashcat` root Type cmd on file explorer => `hashcat.exe -m 22100 Hash.txt example.dict`.
