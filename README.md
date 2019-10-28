# README

## OASIS TC Open Repository: openc2-iosacl-adapter

This GitHub public repository (**[https://github.com/oasis-open/openc2-iosacl-adapter/](https://github.com/oasis-open/openc2-iosacl-adapter/)**) was created at the request of the [OASIS Open Command and Control (OpenC2) TC](https://www.oasis-open.org/committees/openc2/) as an [OASIS TC Open Repository](https://www.oasis-open.org/resources/open-repositories/) to support development of open source resources related to Technical Committee work.

While this TC Open Repository remains associated with the sponsor TC, its development priorities, leadership, intellectual property terms, participation rules, and other matters of governance are [separate and distinct](https://github.com/oasis-open/openc2-iosacl-adapter/blob/master/CONTRIBUTING.md#governance-distinct-from-oasis-tc-process) from the OASIS TC Process and related policies.

All contributions made to this TC Open Repository are subject to open source license terms expressed in the [MIT License](https://www.oasis-open.org/sites/www.oasis-open.org/files/MIT-License.txt). That license was selected as the declared [Applicable License](https://www.oasis-open.org/resources/open-repositories/licenses) when the TC Open Repository was created.

As documented in [Public Participation Invited](https://github.com/oasis-open/openc2-iosacl-adapter/blob/master/CONTRIBUTING.md#public-participation-invited), contributions to this OASIS TC Open Repository are invited from all parties, whether affiliated with OASIS or not. Participants must have a GitHub account, but no fees or OASIS membership obligations are required.  Participation is expected to be consistent with the [OASIS TC Open Repository Guidelines and Procedures](https://www.oasis-open.org/policies-guidelines/open-repositories), the open source [LICENSE](https://github.com/oasis-open/openc2-iosacl-adapter/blob/master/LICENSE.md) designated for this particular repository, and the requirement for an [Individual Contributor License Agreement](https://www.oasis-open.org/resources/open-repositories/cla/individual-cla) that governs intellectual property.

## Statement of Purpose

- To demonstrate an adapter translating OpenC2 commands to Cisco IOS format (syntax) for Access Control Lists (ACLs) management, and

- Provide an R code base to facilitate other prototype efforts,

### openc2-iosacl-adapter

The openc2-iosacl-adapter is a software tool (Proof of Concept) written in R for parsing, translating, and executing OpenC2 commands to CISCO devices running IOS (Internetwork Operating System) and support Access Control Lists (ACL). All the activity, response codes and messages are stored into a database.

The repository contains source code (multiple interdependent R files) [here](https://github.com/oasis-open/openc2-iosacl-adapter/tree/master/code), sample actuator/consumer schema and recommended information for inclusion [here](https://github.com/oasis-open/openc2-iosacl-adapter/tree/master/sample-actuator-information-file), OpenC2 sample commands for experimentation [here](https://github.com/oasis-open/openc2-iosacl-adapter/tree/master/sample-openc2-slpf-commands) and [here](https://github.com/oasis-open/openc2-iosacl-adapter/tree/master/sample-openc2-slpf-commands-for-terminal-use), and some other folders containing Cisco-related details to assist in the configuration of the actuator . The tool can be used as a command-line tool or as a R library which can be included in other applications.

### Quickstart


*"Rscript openc2_iosacl_adapter.R -- help"* will show all the available options

```
-o OPENC2, --openc2=OPENC2
                OpenC2 command in JSON - The command needs to be given as a single line enclosed in single quotation marks

        -f FILE, --file=FILE
                file including one or more OpenC2 commands in JSON - optimally, full path should be given

        -a ACTUATORS, --actuators=ACTUATORS
                consumer/actuator information file

        -h, --help
                Show this help message and exit
```


Execute an OpenC2 command
```
Execute "Rscript openc2_iosacl_adapter.R -o *'OpenC2_command_enclosed_in_single_quotations'* -a *actuators information file*
```
**Prerequisites**
1. R - https://www.r-project.org/

2. Python 2 or 3 - https://www.python.org/

3. Netmiko - "pip install netmiko" or check [here](https://pypi.org/project/netmiko/)

3. Configuration file including relevant actuator/consumer information. You can find an example file that references the appropariate schema [here](https://github.com/oasis-open/openc2-iosacl-adapter/tree/master/sample-actuator-information-file)

For example:
```
      { 
         "asset_id":"10",
         "description":"OSLO-UIO-cisco-edge-router-slpf-ingress",
         "network":{ 
            "interface":"WAN",
            "hostname":"10.10.10.1",
            "port":8080,
            "username":"user1",
            "password":"12345",
            "direction":"ingress",
            "acl_id":"wan_inbound",
            "acl_type":"ipv4"
         }
      }
  ```
**Required** name/value pairs for the actuator communication [actuators.json](https://github.com/oasis-open/openc2-iosacl-adapter/blob/master/sample-actuator-information-file/actuators.json) are:
1. asset_id
2. network
    - hostname
    - port
    - username
    - password
    - acl_id
    - acl_type


## Author

- Vasileios Mavroeidis - vasileim@ifi.uio.no GitHub ID: https://github.com/Vasileios-Mavroeidis - [University of Oslo](https://www.mn.uio.no/ifi/english/people/aca/vasileim/)

## Maintainers

TC Open Repository [Maintainers](https://www.oasis-open.org/resources/open-repositories/maintainers-guide) are responsible for oversight of this project's community development activities, including evaluation of GitHub [pull requests](https://github.com/oasis-open/openc2-iosacl-adapter/blob/master/CONTRIBUTING.md#fork-and-pull-collaboration-model) and [preserving](https://www.oasis-open.org/policies-guidelines/open-repositories#repositoryManagement) open source principles of openness and fairness. Maintainers are recognized and trusted experts who serve to implement community goals and consensus design preferences.

Initially, the associated TC members have designated one or more persons to serve as Maintainer(s); subsequently, participating community members may select additional or substitute Maintainers, by [consensus](https://www.oasis-open.org/resources/open-repositories/maintainers-guide#additionalMaintainers).

The current Maintainers of this TC Open Repository

- Vasileios Mavroeidis - vasileim@ifi.uio.no GitHub ID: https://github.com/Vasileios-Mavroeidis - [University of Oslo](https://www.mn.uio.no/ifi/)

- David Lemire - dave.lemire@g2-inc.com GitHub ID: https://github.com/dlemire60 - [G2](https://www.g2-inc.com/)

## About OASIS TC Open Repositories

- [TC Open Repositories: Overview and Resources](https://www.oasis-open.org/resources/open-repositories/)

- [Frequently Asked Questions](https://www.oasis-open.org/resources/open-repositories/faq)

- [Open Source Licenses](https://www.oasis-open.org/resources/open-repositories/licenses)

- [Contributor License Agreements (CLAs)](https://www.oasis-open.org/resources/open-repositories/cla)

- [Maintainers' Guidelines and Agreements](https://www.oasis-open.org/resources/open-repositories/maintainers-guide) 

## Feedback

Questions or comments about this TC Open Repository's activities should be composed as GitHub issues or comments. If use of an issue/comment is not possible or appropriate, questions may be directed by email to the Maintainer(s) listed above. 

Please send general questions about TC Open Repository participation to OASIS Staff at repository-admin@oasis-open.org and any specific CLA-related questions to repository-cla@oasis-open.org.
