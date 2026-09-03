## Static Analysis with Cutter — Steps
## Step 1 — Update Kali

Update the Kali repositories:

sudo apt update

Expected: Update completes without NO_PUBKEY or repository is not signed errors.


## Step 2 — Check Kali Repository
cat /etc/apt/sources.list

If needed:

cat /etc/apt/sources.list.d/kali.sources
## Step 3 — Install Rizin
sudo apt install rizin

Verify:

rizin -v

## Step 4 — Download and Run Cutter

Download the Linux x86_64 AppImage from the official Cutter website.

Then:

cd ~/Downloads

Check the file:

ls

Make it executable:

chmod +x Cutter*.AppImage

Run Cutter:

./Cutter*.AppImage



## Step 5 — Create Project Folders
mkdir -p ~/binary-analysis/screenshots
mkdir -p ~/binary-analysis/report
cd ~/binary-analysis

Check:

tree
## Step 6 — Create a Sample C Program
nano main.c

Add:

#include <stdio.h>

int main() {
    printf("Hello World\n");
    return 0;
}
## Step 7 — Compile the Program
gcc main.c -o sarra

Verify:

file sarra

Run it:

./sarra
## Step 8 — Calculate File Hash
sha256sum sarra


## Step 9 — Open the Executable in Cutter
cutter ./sarra
## Step 10 — Analyze File Information

In Cutter, examine:

File format
Architecture
Bitness
Entry point
Sections
Security properties



## Step 11 — Analyze Strings

Terminal:

strings sarra

In Cutter, check the Strings panel.



## Step 12 — Analyze Imports

In Cutter, open Imports and examine the imported functions.



## Step 13 — Analyze Functions

Open Functions and identify the functions shown by Cutter.


## Step 14 — Analyze Entry Point

Open the entry-point function and examine where execution begins.


## Step 15 — Analyze Disassembly

Open main and examine the assembly instructions.

Look for instructions such as:

mov
push
lea
call
pop
ret

## Step 16 — Analyze Graph View

Switch to Graph View and examine the control flow and basic blocks.


## Step 17 — Analyze Decompiled Code

Open the Decompiler and compare the C-like output with your original source.



## Step 18 — Analyze Cross-References

Check Xrefs for strings, functions, or addresses to see where they are referenced.


