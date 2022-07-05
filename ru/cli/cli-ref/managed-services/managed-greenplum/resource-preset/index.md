---
sourcePath: ru/_cli-ref/cli-ref/managed-services/managed-greenplum/resource-preset/index.md
---
# yc managed-greenplum resource-preset

Manage Greenplum resource presets

#### Command Usage

Syntax: 

`yc managed-greenplum resource-preset <group>`

Aliases: 

- `resource-presets`

#### Command Tree

- [yc managed-greenplum resource-preset get](get/index.md) — Show information about the specified Greenplum resource preset
	- [yc managed-greenplum resource-preset get master](get/master.md) — Show information about the specified Greenplum resource preset for master.
	- [yc managed-greenplum resource-preset get segment](get/segment.md) — Show information about the specified Greenplum resource preset for segment.
- [yc managed-greenplum resource-preset list](list/index.md) — List available Greenplum resource presets.
	- [yc managed-greenplum resource-preset list master](list/master.md) — List available Greenplum resource presets for master hosts.
	- [yc managed-greenplum resource-preset list segment](list/segment.md) — List available Greenplum resource presets for segment hosts.

#### Global Flags

| Flag | Description |
|----|----|
|`--profile`|<b>`string`</b><br/>Set the custom configuration file.|
|`--debug`|Debug logging.|
|`--debug-grpc`|Debug gRPC logging. Very verbose, used for debugging connection problems.|
|`--no-user-output`|Disable printing user intended output to stderr.|
|`--retry`|<b>`int`</b><br/>Enable gRPC retries. By default, retries are enabled with maximum 5 attempts. Pass 0 to disable retries. Pass any negative value for infinite retries. Even infinite retries are capped with 2 minutes timeout.|
|`--cloud-id`|<b>`string`</b><br/>Set the ID of the cloud to use.|
|`--folder-id`|<b>`string`</b><br/>Set the ID of the folder to use.|
|`--folder-name`|<b>`string`</b><br/>Set the name of the folder to use (will be resolved to id).|
|`--token`|<b>`string`</b><br/>Set the OAuth token to use.|
|`--format`|<b>`string`</b><br/>Set the output format: text (default), yaml, json, json-rest.|
|`-h`,`--help`|Display help for the command.|