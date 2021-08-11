# command:

## FRONTEND nightly: get difference between today and yesterday

git fetch --quiet && since=$(date --date="-1 day" +%Y-%m-%d)"T03:00:00" && until=$(date +%Y-%m-%d)"T02:59:00" && var=`git rev-list --left-right --count origin/master --since=$since --until=$until  | cut -f2` && if ! [ `echo $var | grep 0` ] ; then echo "FrontEnd ($var):" ; git log origin/master --oneline --since=$since --until=$until | cat | cut -c 10- ; fi

## Frontend monday: 

### get difference between today (Monday) and the day before 4 days (Thursday - my last working day in a week)

git fetch --quiet && since=$(date --date="-4 day" +%Y-%m-%d)"T03:00:00" && until=$(date +%Y-%m-%d)"T02:59:00" && var=`git rev-list --left-right --count origin/master --since=$since --until=$until  | cut -f2` && if ! [ `echo $var | grep 0` ] ; then echo "FrontEnd ($var):" ; git log origin/master --oneline --since=$since --until=$until | cat | cut -c 10- ; fi

### get difference between today and date

git fetch --quiet && since="2020-10-01T03:00:00" && until=$(date +%Y-%m-%d)"T02:59:00" && var=`git rev-list --left-right --count origin/master --since=$since --until=$until  | cut -f2` && if ! [ `echo $var | grep 0` ] ; then echo "FrontEnd ($var):" ; git log origin/master --oneline --since=$since --until=$until | cat | cut -c 10- ; fi

## 2222 get difference between today and yesterday

git fetch --quiet && since="2020-09-29T03:00:00" && until=$(date +%Y-%m-%d)"T02:59:00" && var=`git rev-list --left-right --count origin/master --since=$since --until=$until  | cut -f2` && if ! [ `echo $var | grep 0` ] ; then echo "FrontEnd ($var):" ; git log origin/master --oneline --since=$since --until=$until | cat | cut -c 10- ; fi


## BACKEND: get difference local between origin (if local is behind)

git fetch --quiet && var=`git rev-list --left-right --count origin/master...@ | cut -f1` && if ! [ `echo $var | grep 0` ] ; then echo "BackEnd ($var):" ; git log origin/master --oneline -n $var | cat | cut -c 10- ; fi

## 1. git fetch --quiet

git fetch without output (see https://stackoverflow.com/a/8943761)



## 2. var=`git rev-list --left-right --count origin/master...@ | cut -f1`

store count of how many commits local master is behind of origin master (reduce to output origin master only) to var

see https://stackoverflow.com/a/27940027
and (for var): https://linuxhint.com/bash_command_output_variable/



## 3. if ! [ `echo $var | grep 0` ] ; then echo "FrontEnd ($var):" ; git log --oneline -n $var | cat | cut -c 10- ; fi
===================================================================================================================
grep results with true/false

git log origin/master --oneline -n $var | cat | cut -c 10
---------------------------------------------------------
gives a short git log of last $var commits and cuts the first 9 chars of each line (commit hash)

see
* if: https://unix.stackexchange.com/questions/40568/executing-if-statement-from-command-prompt
* git log: https://stackoverflow.com/a/13542327
* cut: https://stackoverflow.com/a/31240950




error: Die letzte Ausführung von "gc run" enthielt die folgenden Meldungen.
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
Bitte beheben Sie das Hauptproblem und löschen Sie .git/gc.log.
Ein automatischer Cleanup wird nicht ausgeführt, bis diese Datei entfernt
wurde.

fatal: bad object refs/remotes/origin/HEAD
error: failed to run repack

	mv .git/refs/remotes/origin/HEAD /tmp && git gc && git prune

Quelle: https://stackoverflow.com/a/38192799
