# 🔧 rustfmt-config
Version control friendly linting configuration for rustfmt.

## 🚀 Motivation
Popular version control systems (VCSes), such as Git, manage code changes for each line.
That compatibles with codes, generally, but sometimes we experience unneeded line changes caused by other line(s).

For example, in JSON:
```diff
{
-  "foo": "bar"
+  "foo": "bar",
+  "bar": "baz"
}
```

Since JSON does not support trailing comma, we need to change the last line, even if the line is not needed to change.
So JSON can be said as NOT VCS-friendly.

In this repository, I am trying to keep our codes VCS-friendly using rustfmt.

## 💉 Disclaimer
To use VCS-friendly format, unstable rules are also used in this configuration.
In production, disabling these features by setting `unstable_features = false` is recommended.

## ✨ Usage
1. First of all, clone this repository, then move into the directory.
   ```console
   $ git clone https://github.com/siketyan/rustfmt-config.git
   $ cd ./rustfmt-config
   ```

1. Checkout the branch of compatible version with your rustfmt.
   ```console
   $ git switch "v$(rustfmt --version | cut -d ' ' -f2 | cut -d '-' -f1)"
   ```

1. Copy rustfmt.toml into your project directory.
   ```console
   $ cp ./rustfmt.toml ~/path/to/your/project/
   ```
   Creating a symlink is not recommended.
   Changing contents of the file may occur when checkouting another branch.

## 📄 Licence
This configuration is licenced under CC0.
For details, see [LICENCE.md](./LICENCE.md).
