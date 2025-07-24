# APSIMX GitHub Actions

This GitHub **composite action** checks out the APSIM Next Generation source code, installs the .NET SDK, compiles the `Models.csproj` project, and adds the output directory to the system `PATH`. This enables subsequent workflow steps to run APSIMX simulations using `Models`.

## 📦 Features

- Clone APSIMX source code from a specified GitHub repository and branch
- Install .NET SDK (version `8.0.x`)
- Build the `Models` project using `dotnet build`
- Add the compiled output directory (`bin/Release/net8.0`) to the system `PATH`
- Optionally run a test example simulation (`Wheat.apsimx`) to verify the build

## 🔧 Inputs

| Name               | Description                                               | Required | Default                                                  |
|--------------------|-----------------------------------------------------------|----------|----------------------------------------------------------|
| `repo-url`         | GitHub repo of APSIMX source in `org/repo` format         | No       | `APSIMInitiative/ApsimX`                                 |
| `branch`           | Branch to checkout                                        | No       | `master`                                                 |
| `run-test-example` | Whether to run a test example simulation after compiling  | No       | `false` (automatically enabled in `APSIMInitiative/ApsimX`) |

## 🚀 Usage

To use this action in your workflow, reference it with the appropriate path and version:

```yaml
- name: Compile APSIMX
  uses: byzheng/apsimx-action@main
```

**Enable Test Example Run**

To explicitly run the Wheat.apsimx test example (e.g. in your own fork or another repo):

```yaml

- name: Compile and test APSIMX
  uses: byzheng/apsimx-action@main
  with:
    run-test-example: 'true'
```

## 📁 Output

The compiled APSIMX binary (`Models`) is available in the system `PATH`.

