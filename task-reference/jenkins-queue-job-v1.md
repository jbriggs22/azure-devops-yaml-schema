---
title: JenkinsQueueJob@1 - Jenkins Queue Job v1 task
description: Queue a job on a Jenkins server (task version 1).
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# JenkinsQueueJob@1 - Jenkins Queue Job v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Queue a job on a Jenkins server.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Jenkins Queue Job v1
# Queue a job on a Jenkins server.
- task: JenkinsQueueJob@1
  inputs:
    serverEndpoint: # string. Required. Jenkins service endpoint. 
    jobName: # string. Required. Job name. 
    #isMultibranchJob: false # boolean. Job is of Multibranch Pipeline type. Default: false.
    #multibranchPipelineBranch: # string. Required when isMultibranchJob = true. Multibranch Pipeline Branch. 
    captureConsole: true # boolean. Required. Capture console output and wait for completion. Default: true.
    capturePipeline: true # boolean. Required when captureConsole = true. Capture pipeline output and wait for pipeline completion. Default: true.
  # Advanced
    parameterizedJob: false # boolean. Required. Parameterized job. Default: false.
    #jobParameters: # string. Optional. Use when parameterizedJob = true. Job parameters.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="serverEndpoint"::: -->
:::moniker range="<=azure-pipelines"

**`serverEndpoint`** - **Jenkins service endpoint**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the service endpoint for your Jenkins instance.  To create one, click the Manage link and create a new Jenkins service endpoint.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobName"::: -->
:::moniker range="<=azure-pipelines"

**`jobName`** - **Job name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Jenkins job to queue.  This must exactly match the job name on the Jenkins server.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isMultibranchJob"::: -->
:::moniker range="<=azure-pipelines"

**`isMultibranchJob`** - **Job is of Multibranch Pipeline type**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This job is of multibranch pipeline type.  If selected, enter the appropriate branch name. Requires Team Foundation Server Plugin for Jenkins v5.3.4 or later.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="multibranchPipelineBranch"::: -->
:::moniker range="<=azure-pipelines"

**`multibranchPipelineBranch`** - **Multibranch Pipeline Branch**<br>
Type: string. Required when isMultibranchJob = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Queue this Multibranch Pipeline job on the specified branch. Requires Team Foundation Server Plugin for Jenkins v5.3.4 or later.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="captureConsole"::: -->
:::moniker range="<=azure-pipelines"

**`captureConsole`** - **Capture console output and wait for completion**<br>
Type: boolean. Required. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If selected, this step will capture the Jenkins build console output, wait for the Jenkins build to complete, and succeed/fail based on the Jenkins build result.  Otherwise, once the Jenkins job is successfully queued, this step will successfully complete without waiting for the Jenkins build to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="capturePipeline"::: -->
:::moniker range="<=azure-pipelines"

**`capturePipeline`** - **Capture pipeline output and wait for pipeline completion**<br>
Type: boolean. Required when captureConsole = true. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If selected, this step will capture the full Jenkins build pipeline console output, wait for the full Jenkins build pipeline to complete, and succeed/fail based on the Jenkins build pipeline result.  Otherwise, once the first Jenkins job completes, this step will successfully complete without waiting for full Jenkins build pipeline to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parameterizedJob"::: -->
:::moniker range="<=azure-pipelines"

**`parameterizedJob`** - **Parameterized job**<br>
Type: boolean. Required. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select if the Jenkins job accepts parameters. This should be selected even if all default parameter values are used and no parameters are actually specified.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobParameters"::: -->
:::moniker range="<=azure-pipelines"

**`jobParameters`** - **Job parameters**<br>
Type: string. Optional. Use when parameterizedJob = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify job parameters, one per line, in the form <b>`<parameterName>=<parameterValue>`</b><p>To set a parameter to an empty value (useful for overriding a default value), leave off the parameter value. For example, specify <b>`<parameterName>=`</b><p>Variables are supported. For example, to set a <b>`commitId`</b> parameter value to the Git commit ID of the build, use: <b>`commitId=$(Build.SourceVersion)`</b>. See the [documentation on variables](https://www.visualstudio.com/docs/build/define/variables) for more details.<p>Supported Jenkins parameter types are: <ul><li>`Boolean`</li><li>`Choice`</li><li>`Password`</li><li>`String`</li></ul>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Build |

:::moniker-end

:::moniker range="=azure-pipelines-2018"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | All |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->