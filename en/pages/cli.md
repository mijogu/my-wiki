## Command Line / ZSH

http://zsh.sourceforge.net/

mkdir
cd
diff
date
cal

mv
Use mv to rename files.


cp
cp -a /source/. /dest/

pwd (tells you where you are)

create file(s)
touch .gitignore
touch file1.txt file2.txt file3.txt

foreach loop
for x in 1 2 3; do echo $x; done
for x in twentyseventeen twentytwenty; do wp theme delete $x; done

Use trash instead of rm, will send to Trash Can
trash file.txt file2.txt

Force reload .zshrc after changes.
source ~/.zshrc

MAMP Aliases (defined in .zshrc)ps
startmamp
stopmamp

alias startmamp='open /Applications/MAMP\ PRO.app; /Applications/MAMP/bin/start.sh' 
alias stopmamp='/Applications/MAMP/bin/stop.sh'

Get list of running processes, and PIPE that thru Regex search. 
Then use the appid to kill program. 
ps = Process Status
ps aux | grep MAMP
sudo kill {xxxxx}

pgrep {programname}
pkill {programname}

Print PHP info, and PIPE that thru searching for php.ini filepath.
php -i | grep php.ini

Open file with VS Code
code filename

Use file as input
command < file

Create file from output
command > file

Append to a file
command >> file

Run process in background
command &

Place a running process in the background.
<control>z 
then enter
bg 
(or enter fg to bring back)

find . -name "pattern" -print

man command (show manual for command)

cat (concatenate)
cat filename filename2 (displays contents of file(s))
cat -n filename (with line numbers)

Make file executable
chmod +x ~/Scripts/config.sh

