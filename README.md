# apsimx-actions

This GitHub composite action checks out the APSIM Next Generation source code, installs the .NET SDK, compiles the `Models.csproj` project, and adds the output directory to the system `PATH`. This enables subsequent workflow steps to run APSIMX simulations using `Models.exe`.

## 📦 Features

- Clone APSIMX source code from a specified repository and branch
- Install .NET SDK (version 8.0.x)
- Build the `Models` project using `dotnet build`
- Add the compiled binary directory to the system `PATH`

## 🔧 Inputs

| Name       | Description                     | Required | Default                                                  |
|------------|---------------------------------|----------|----------------------------------------------------------|
| `repo-url` | Git URL of APSIMX source        | No       | `https://github.com/APSIMInitiative/ApsimX.git`         |
| `branch`   | Branch to checkout              | No       | `master`                                                 |

## 🚀 Usage

To use this action in your workflow, reference it with the appropriate path and version:


```

- name: Compile APSIMX
  uses: byzheng/apsimx-action/.github/actions/compile-apsimx@main
```