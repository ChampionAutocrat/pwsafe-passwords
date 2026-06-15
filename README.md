<div align="center">

# Password Safe Manager

Secure and convenient password management with CodeLite build workspace guidance.

</div>

## 🔐 Overview

Password Safe is a password manager described as a popular, secure, and convenient way to manage passwords. This README focuses on the available project information for working with Password Safe through the CodeLite IDE on Linux.

The provided project notes are centered on building and browsing Password Safe using CodeLite rather than using makefiles. They describe how to configure CodeLite for a wxWidgets 3.x-based build, how to set editor preferences to avoid unintended whitespace changes, and how the included workspace projects are intended to be used.

## 🧰 Development Environment

Password Safe uses **wxWidgets 3.x**. Because some Linux distributions may not ship wxWidgets 3.x by default, you may need to build wxWidgets 3.x separately and configure CodeLite so it can find the correct headers and libraries.

| Component | Purpose |
|---|---|
| CodeLite | IDE used to browse, build, and debug Password Safe |
| wxWidgets 3.x | GUI toolkit required by the wxWidgets build |
| wx-config | Used by CodeLite to locate wxWidgets build configuration |

CodeLite should be able to see the following environment variables:

```text
WX3_CONFIG_DEBUG=<path to wx-config of your wx3 debug build>
WX3_CONFIG_RELEASE=<path to wx-config of your wx3 release build>
```

These variables should point to the `wx-config` files for the debug and release builds of wxWidgets 3.x.

## 🛠️ Building with CodeLite

To build Password Safe using CodeLite:

1. Launch CodeLite.
2. Open the workspace through **Workspace → Switch to Workspace...**.
3. Select the `PasswordSafe.workspace` file.
4. In the Workspace view, right-click `pwsafe` under the `PasswordSafe` root item.
5. Choose **Build**.

Alternatively, use **Build → Build Workspace** from the CodeLite menu.

Depending on the selected configuration, CodeLite creates a `Debug` or `Release` directory under the CodeLite workspace directory. The build output described in the project notes includes intermediate and final build artifacts such as:

- `libcore.a`
- `libos.a`
- `pwsafe`

## ✍️ Recommended CodeLite Editor Settings

The project notes recommend specific indentation settings when editing Password Safe source code in CodeLite. These settings help reduce unintended whitespace changes.

Recommended settings:

1. Do not use tabs.
2. Use 2-character indentation.
3. Convert each tab to 2 spaces.

In CodeLite, these can be configured from:

**Settings → Global Editor Preferences → General → Indentation**

Suggested values:

- Uncheck **Use tabs in indentation**
- Set **Columns per indentation level** to `2`
- Set **Columns per tab character in document** to `2`

If you only want these settings to apply to the Password Safe workspace, use **Workspace Editor Preferences** for the `PasswordSafe` workspace and override the global indentation settings there.

Before committing changes, review diffs carefully to ensure that unrelated whitespace changes are not included.

## 🧭 Workspace Projects

The CodeLite workspace includes projects that serve different purposes.

### Password Safe project

The `pwsafe` project is the main build target used when building Password Safe from CodeLite.

### Windows project

The `Windows` project exists for browsing the source files related to the Windows/MFC build. It is not described as a build target when building `pwsafe` or the full workspace.

### wxWidgets project

The `wxWidgets` project exists to make wxWidgets source code easier to browse from within CodeLite. It assumes wxWidgets sources are available in a `wx` subdirectory under the CodeLite directory.

For example, if wxWidgets sources are located at `/usr/src/wxGTK-2.8.10/`, the project notes suggest creating a symlink named `wx` pointing to that directory.

This project is intended for source browsing, symbol cross-referencing, and debugging convenience. It is not described as a build target.

## ✅ Practical Notes

- The CodeLite files are intended to make browsing, building, and debugging Password Safe more convenient.
- wxWidgets 3.x must be available and visible to CodeLite.
- Editor indentation settings matter because CodeLite may adjust whitespace depending on configuration.
- The Windows and wxWidgets workspace projects are provided for navigation and reference, not as active build targets.

## ❓ FAQ

### What is Password Safe?

Password Safe is a password manager described as secure, convenient, and popular.

### What is this README focused on?

This README summarizes the available CodeLite workspace guidance for building and browsing Password Safe.

### Does Password Safe require wxWidgets?

The provided project notes state that Password Safe uses wxWidgets 3.x.

### Can CodeLite be used instead of makefiles?

Yes. The project notes describe using CodeLite to build Password Safe as an alternative to makefiles.

### Are the Windows and wxWidgets projects build targets?

No. The available notes describe them as browsing/reference projects, not as build targets for the main CodeLite build.

### Why are indentation settings mentioned?

The project notes warn that CodeLite may adjust whitespace depending on editor settings, so consistent indentation settings are recommended.
