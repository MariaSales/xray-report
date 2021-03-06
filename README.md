# xray-report 
  
Jira [Xray](https://www.getxray.app/) plugin for [Gauge](http://gauge.org)  

Please note that this is a preview release and am looking for feedback on:

- What a failure report should look like and contain
- Upload Gauge specs to autocreate Xray tests

I will soon release a Jira plugin that allows Xray tests to render Gauge Specs with formatting and syntax highlighting. 

Installation
------------

```bash
gauge install xray-report
```

#### Installing specific version:

```bash
gauge install xray-report --version 0.1.1
```

#### Offline installation
* Download the plugin from [Releases](https://github.com/jbadeau/xray-report/releases)

```bash
gauge install xray-report --file <path_to_plugin_zip_file>
```

Usage
-----

Add this plugin to your Gauge project by registering it in `manifest.json` file. You can also do this by:

```bash
{
  "Language": "",
  "Plugins": [
    "xray-report"
  ]
}
```

#### Provide the following env variables
```properties
jira_url = https://your.jira.url
jira_username = <user>
jira_password = <password>
jira_authentication = cookie/basic
```
> Do **NOT** save the 'jira_password' in source code. 

> Default jira_authentication is cookie if property not provided.

#### Add **TestCaseId:\<XrayTestKey>** tag to scenarios

```markdown  
## Scenario
Tags: TestCaseId:PROJECT-1
```

#### Reuse Test Execution

In order to avoid creating a new test execution for each run, add **TestExecutionId:\<XrayTestExecutionKey>** tag to spec 

```markdown  
# Spec
Tags: TestExecutionId:PROJECT-2
```
