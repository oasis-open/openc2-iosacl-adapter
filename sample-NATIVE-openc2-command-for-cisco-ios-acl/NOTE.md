## Note

Cisco ACL configuration demands information that are not part of an OpenC2 command per the official OpenC2 specifications. The native-openc2-command-cisco-ios-acl.json file includes an OpenC2 command with Cisco-relevant information for the configuration of ACLs. This command would be appropriate to be sent to a Native Cisco_IOS interface. Note: That this is just an idea and is not in any case supported by Cisco.

The command at https://github.com/oasis-open/openc2-iosacl-adapter/blob/master/sample-NATIVE-openc2-command-for-cisco-ios-acl/native-openc2-command-cisco-ios-acl.json does not work with the openc2-iosacl-adapter since it is not conformant to the language specification v1.0. The same information is parsed from the actuators.json (https://github.com/oasis-open/openc2-iosacl-adapter/blob/master/sample-actuator-information-file/actuators.json) file when an asset id is specified to an OpenC2 command.
