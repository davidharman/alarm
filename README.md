# alarm
Alarm in Bash with the use of termdown (https://github.com/trehn/termdown).

I wanted:
- a simple alarm which can be set via a terminal (e.g. Bash, Zsh, etc)
- Only need to provide an hour and minute and optional text
- a countdown to show how long left
- start and stop times to be shown if CTRL+C is shown 


First install TermDown
<i>pip install termdown</i>

Then place the alarm script from this repo in to your bin folder

Now run Alarm, command is alarm <time> [Text] [Font]
  Text and Font are optional, if no text then it defaults to the word Alarm

alarm 10:00 Meeting starwars

alarm 13:50 'Staff Meeting'

You will now get a timer for the remaining minutes showing the word meeting in the starwars font from now until 10:00 and at the end a beep will sound.
