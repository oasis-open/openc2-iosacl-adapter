## Note

The file openc2-terminal-commands includes sample "one line" (flattened) OpenC2 commands for terminal use. The user needs to launch a terminal and navigate to the folder that the openc2-ios-acl-adapter code files are. From there we use the "openc2_iosacl_adapter.R" file to issue an OpenC2 command to an actuator. For example, *Rscript openc2_iosacl_adapter.R -o 'OpenC2 command' -a 'path of the file that has information about the actuators'*. The appropriate schema to create json objects to indicate actuator information can be found at https://github.com/oasis-open/openc2-iosacl-adapter/blob/master/sample-actuator-information-file/actuators.json

Possible parameters are:

-o  OPENC2, --openc2=OPENC2
OpenC2 command in JSON - The command needs to be given as a single line enclosed in single quotation marks

-f  FILE, --file=FILE
path of a file with one or more OpenC2 commands in JSON - optimally, full path should be specified

-a  ACTUATORS, --actuators=ACTUATORS
consumer/actuator information file

You can find the file at https://github.com/oasis-open/openc2-iosacl-adapter/blob/master/sample-openc2-slpf-commands-for-terminal-use/openc2-terminal-commands.txt
