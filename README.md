# radio-launcher
A bash script for launching and managing a Liquid Soap stream

-------

Usage: SCRIPTNAME {start|stop|restart|request|skip|configs|help}
_____

You can type: 'SCRIPTNAME help {start|stop|restart|request|skip|configs|help}'
for detailed help on any specific command

   Start
   _____

   Usage:
    SCRIPTNAME start <path to music directory> <stream title> <stream description> {randomize|normal}

   Generates playlist of chosen directory, generates and then runs the 'liq' script.
   If 'saveconfig' is set to 1 at the top of this script, the specified values will
   be stored in the default config file to allow for easy subsequent starts.
   Additionally it corrects the permissions on the socket file to allow group usage.


   Special Usage:
    SCRIPTNAME start config <config file (optional)>

   This this will use the chosen config file to generate the required setup (if the file exists).
   If the config file is omitted, the default config file will be used.  If neither exist, default
   values will be substitute.

   Stop
   ____

   Usage:
    SCRIPTNAME stop

   Stops the associated liquidsoap instance if it's currently running.

   Restart
   ____

   Usage:
    SCRIPTNAME restart

   Stops the associated liquidsoap instance if it's currently running.
   Then starts it using the default config file.  If 'setconfig' is set to 1, then this will
   contain the settings used on last run, and it will start as it was prior to the restart.
   If not, the script will start with the same conditions as if you used the form:

   SCRIPTNAME start config

   Request
   ____

   Usage:
    SCRIPTNAME request <path to music file>

   This will connect to the socket for the associated liquidsoap instance, and submit a
   request based on the file specified.

   Skip
   ____

   Usage:
    SCRIPTNAME skip

   This will connect to the socket for the associated liquidsoap instance, and will send
   a skip command for the current stream.

   Configs
   ____

   Usage:
    SCRIPTNAME configs

   This will output a list of the available parameters for use with
    'SCRIPTNAME start config <config file>'

