## Building and installing cmatrix
To install cmatrix, use either of the following methods from within the cmatrix directory.

#### Using `configure` (recommended for most linux user)
```
autoreconf -i  # skip if using released tarball
./configure
make
make install
```
### Running cmatrix
After you have installed cmatrix just run `ncmatrix` to run ncmatrix :)


example Usage: `ncmatrix -b -C white -I lo -R red -T yellow`


```
NCMatrix - a popular scrolling screensaver with network traffic display
------------------------------------------------------------------------------
NCMatrix is based on the original CMatrix scrolling "screen saver"
by Chris Allegretta.  I was sitting around one day looking at it
run on my gateway and thought "That's a kick-ass screen but it would
be cool if it were a bit more functional"  so I decided to hack in
some code to make it display network activity.  I tried contacting 
the author to get his input on this but for whatever reason, I recieved
no reply.  Everything is GPL, so rock on.

What NCMatrix does is inject different colored streams of character
data into the display based on incoming and outgoing packets of the
network interface. NCMatrix at rest will simply display the familiar
streams of character data, however when the network traffic picks-up,
the displayed characters adjust accordingly.

I've also added command line switches which are:

 -C [color]: Use this color for matrix (default green)
 -I [nic]  : Use this network interface for data (/proc/net/dev)
 -H [limit]: threshold for reporting network traffic (loop trigger).
 -R [color]: Use this color for recieved packets.
 -T [color]: Use this color for transmitted packets.


Read the manpage for more details, or nroff -man ncmatrix.1 from the
tarball.


ncmatrix --help gives:

   Usage: ncmatrix -[abBfhlsVx] [-u delay] [-C color] [-I nic] [-H limit] [-R color] [-T color]
   
So a command line to start ncmatrix monitoring eth1 in screensaver 
mode with bold characters turned on, a 10 microsecond delay using 
the color red for outgoing packets and magenta for recieved packets
would be:

   ncmatrix -s -b -u 10 -I eth1 -T red -R magenta
   
On slow connections (dial-up slow) you may never get a real impressive 
display of characters, so the -H value will wait a certain number of
times through the info gathering loop before reporting.  This works
well in theory, however I have broadband so I couldn't mess around
testing it much.  Setting the loop trigger woulld look
something like this:

   ncmatrix -s -b -u 10 -I eth1 -T red -R magenta -H 500
   
You would want to adjust the -H parameter accordingly.  I do not
know what the limit of the -H parameter is.  Setting it to 6000 didn't
seem to print anything.


To build ncmatrix, simply run ../configure; make; make install.
Be sure to have the ncurses development libs installed.



...original dox by Chris (CMatrix author) follow below..


CMatrix - show a scrolling 'Matrix' like screen in Linux (curses based)
------------------------------------------------------------------------------

CMatrix Homepage - be sure to check out the latest version =-)
http://www.asty.org/cmatrix

To compile the program, type 'make'.

CMatrix by default operates in 'eye candy' mode.  It must be aborted with
control-c or 'q'.  If you wish for more of a 'screen saver' effect, you
must specify -s on the command line.  For usage, use cmatrix -h.

  To get the program to look most like the movie, use cmatrix -lba
  To get the program to look most like the Win/Mac screensaver, use
  cmatrix -ol

   You'll probably need a decent ncurses library to get this to work. I
have provided a binary that depends on ncurses 4.2 & glibc6.
   If you have any suggestions/flames/patches to send, please feel free to
do so.  Please do not critique my code, I know I'm a hack ;-)  I just got
the urge to write this one evening, and decided to see how fast I could do
it.  It's probably not particularly portable or efficient, but I'm pretty
sure it wont hog *too* much CPU time.

Chris Allegretta
chrisa@asty.org

Thanks to:
- Krisjon Hanson and Bjoern Ganslandt for helping with bold support and 
  Bjoern again for the cursor removal code, helping with the -u and -l
  modes/flags, and Makefile improvements.
- Adam Gurno for multi-color support.
- Garrick West for debian consolefont dir support.
- nemo for design thoughts and continuous help and support.
- John Donahue for helping with transparent term support
- Ben Esacove for Redhat 6 compatibility w/matrix.psf.gz
- Everyone who has been sending (and who will send) me mail regarding
  bugs, comments, patches or just a hello. =-)
- jwz for the xmatrix module to xscreensaver at http://www.jwz.org/xscreensaver.
- My girlfriend Amy for not killing me when I stayed up till 3AM writing this =)
- The makers of the Matrix for one kickass movie!

This software is provided under the GNU GPL.  I am in no way affiliated
in any way with the movie 'The Matrix', just a big fan.

```
