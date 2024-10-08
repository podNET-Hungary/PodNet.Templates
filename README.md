# PodNet.Templates [![NuGet](https://img.shields.io/nuget/v/PodNet.Templates)](https://www.nuget.org/packages/PodNet.Templates/)
Custom templates for `PodNet` packages

## Usage

```cmd
$> dotnet new install PodNet.Templates
```

The command above will install the templates contained in this package. Then, you can use the templates in `dotnet new`:

```cmd
$> dotnet new pod-nuget-repo ^
        --sdkVersion "9.0.100-rc" ^
        --targetFramework "net9.0" ^
        --langVersion "13.0" ^
        --description "Hello world!" ^
        --packageTags "hello, world"
```

> [NOTE!] In CMD, `^` is used to denote a multiline command (`\` in Bash, `` ` `` in PowerShell). It's only shown here for presentation purposes. You can write the parameters in one line without the `^`.

At v1.0.0, only one template is available, see below.

### Templates included

Invoke the template by passing its short name to `dotnet new`.

> This package is a [template package](https://learn.microsoft.com/en-us/dotnet/core/tools/custom-templates) distributed via NuGet; not a package to take direct dependency on in your project. This means that you shouldn't just install the project by `dotnet add package` (even though you can, but it wouldn't achieve anything meaningful).

#### `pod-nuget-repo`

Creates a solution with a corresponding layout and project structure that is used across all `PodNet.*` packages - yes, including this one. The layout of this repository was created by this template as well. Note that many of these could be parameterized, but it's easier to just create the solution as-is and make the modifications after it has been created. On the other hand, as all `PodNet.*` packages, this one is also *opinionated*. The following parameters are required because they usually require your explicit attention, and it makes the package more evergreen.

|Parameter|Description|Required?|Default|
|---|---|---|---|
|description|The `Description` field used by the resulting NuGet package. Also included by default in README.md.|yes||
|packageTags|The additional `PackageTags` used by the NuGet package (besides the now-standard `PodNet` and `awesome` tags).|yes||
|sdkVersion|The value of the SDK to be used in `global.json`. Take care to define a specific version when using preview so that the CI/CD install script can pick up the correct version.|yes||
|targetFramework|The `TargetFramework` MSBuild property to set in each project. To be unambigous, it's best practice to set this in all projects, rather than `Directory.Build.props` or other common MSBuild project files.|yes||
|langVersion|The `LangVersion` MSBuild property to set in `Directory.Build.props`. You can override per-project or using other mechanisms (`Import`ing MSBuild project files, additional `Directory.Build.props` files in the hierarchy, etc.).|yes||

## Contributing and Support

This project is intended to be widely usable, but no warranties are provided. If you want to contact us, feel free to do so in the org's [[Discussions](https://github.com/orgs/podNET-Hungary/discussions/)], at our website at [podnet.hu](https://podnet.hu), or find us anywhere from [LinkedIn](https://www.linkedin.com/company/podnet-hungary/) to [Meetup](https://www.meetup.com/budapest-net-meetup/), [YouTube](https://www.youtube.com/@podNET) or [X](https://twitter.com/podNET_Hungary).

Any kinds of contributions from issues to PRs and open discussions are welcome!

Don't forget to give us a ⭐ if you like this repo (it's free to give kudos!) or share it on socials!

## Sponsorship

If you're using our work or like what you see, consider supporting us. Every bit counts. 🙏 [See here for more info.](https://github.com/podNET-Hungary/PodNet.NuGet.Core/blob/main/src/PodNet.NuGet.Core/build/SPONSORS.md)