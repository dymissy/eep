EEP
---
This is a fork from [mugoweb/eep](https://github.com/mugoweb/eep).

## Commands:

* attribute*
* contentclass*
* contentclassgroup*
* contentnode
* contentobject
* create
* crondaemon
* ezfind
* help*
* knowledgebase*
* list*
* section*
* trash*
* use*


## Usage:

Before to start, you need to register your eZ Publish installation:

    cd /path/to/ezpublis_legacy
    eep use ezroot .
    
### Create a new Content Group

* Create a new Content Group:

		eep contentclassgroup creategroup <group name>


### Create a new Content Class

* List of content classes

		eep list contentclasses
	
* Create a new content class

		eep contentclass createclass <DisplayClassName> <Group>
		eep contentclass createclassuse  News Content

* List attributes of a content class

		eep contentclass listattributes <class identifier>

* Set the class as container 

		eep contentclass setiscontainer <class identifier> <0|1>

* Add a new attribute to the content class

		eep attribute newattributexml #dumps the xml
		eep attribute update <class identifier> <path to xml file>

* Set the string used to name the instances of the class

		eep contentclass setclassobjectidentifier <class identifier> <object naming string or pattern>

### Create Dummy Content

You can create dummy content for each content class. 

	eep use contentclass <class identifier>
	eep use contentnode <parent node id>
	eep create content random

Loop: 

	for i in {1..10}; do eep create content random; echo $i; done

Attributes currently supported:

* ezkeyword
* ezstring
* eztext
* ezdatetime
* ezxmltext
