
```
pixi run build-one opengrep/opengrep --force
```

```
$ tree -F test-output -L 2
test-output/
├── build.sh
├── env.sh
├── linux-64/
│   ├── opengrep-1.22.0-0/
│   ├── opengrep-1.23.0-0/
│   ├── opengrep-1.24.0-0/
│   ├── opengrep-1.25.0-0/
│   ├── opengrep-1.26.0-0/
│   ├── opengrep-1.27.0-0/
│   ├── opengrep-1.27.1-0/
│   ├── opengrep-1.28.0-0/
│   ├── opengrep-1.29.0-0/
│   └── opengrep-1.30.0-0/
├── linux-aarch64/
│   ├── opengrep-1.22.0-0/
│   ├── opengrep-1.23.0-0/
│   ├── opengrep-1.24.0-0/
│   ├── opengrep-1.25.0-0/
│   ├── opengrep-1.26.0-0/
│   ├── opengrep-1.27.0-0/
│   ├── opengrep-1.27.1-0/
│   ├── opengrep-1.28.0-0/
│   ├── opengrep-1.29.0-0/
│   └── opengrep-1.30.0-0/
├── osx-64/
│   ├── opengrep-1.22.0-0/
│   ├── opengrep-1.23.0-0/
│   ├── opengrep-1.24.0-0/
│   ├── opengrep-1.25.0-0/
│   ├── opengrep-1.26.0-0/
│   ├── opengrep-1.27.0-0/
│   ├── opengrep-1.27.1-0/
│   ├── opengrep-1.28.0-0/
│   ├── opengrep-1.29.0-0/
│   └── opengrep-1.30.0-0/
├── osx-arm64/
│   ├── opengrep-1.22.0-0/
│   ├── opengrep-1.23.0-0/
│   ├── opengrep-1.24.0-0/
│   ├── opengrep-1.25.0-0/
│   ├── opengrep-1.26.0-0/
│   ├── opengrep-1.27.0-0/
│   ├── opengrep-1.27.1-0/
│   ├── opengrep-1.28.0-0/
│   ├── opengrep-1.29.0-0/
│   └── opengrep-1.30.0-0/
├── status.txt
└── win-64/
    ├── opengrep-1.22.0-0/
    ├── opengrep-1.23.0-0/
    ├── opengrep-1.24.0-0/
    ├── opengrep-1.25.0-0/
    ├── opengrep-1.26.0-0/
    ├── opengrep-1.27.0-0/
    ├── opengrep-1.27.1-0/
    ├── opengrep-1.28.0-0/
    ├── opengrep-1.29.0-0/
    └── opengrep-1.30.0-0/

56 directories, 3 files
```

I checked all files in `*/opengrep-1.30.0-0/recipe.yaml`:

- `linux-64` -> `https://github.com/opengrep/opengrep/releases/download/v1.30.0/opengrep_manylinux_x86`
- `linux-aarch64` -> `https://github.com/opengrep/opengrep/releases/download/v1.30.0/opengrep-core_linux_aarch64.tar.gz`
- `osx-64` -> `https://github.com/opengrep/opengrep/releases/download/v1.30.0/opengrep_osx_x86`
- `osx-arm64` -> `https://github.com/opengrep/opengrep/releases/download/v1.30.0/opengrep-core_osx_aarch64.tar.gz`
- `win-64` -> `https://github.com/opengrep/opengrep/releases/download/v1.30.0/opengrep_windows_x86.exe`

And tested the `linux-64` conda package with:

- ```
  $ pixi add "$(realpath test-output/linux-64/opengrep-1.30.0-0/test-output/packages/linux-64/opengrep-1.30.0-hb0f4dca_0.conda)"
  ✔ Added ~/octoconda/test-output/linux-64/opengrep-1.30.0-0/test-output/packages/linux-64/opengrep-1.30.0-hb0f4dca_0.conda
  ```

- ```
  $ pixi run which opengrep
  ~/octoconda/.pixi/envs/default/bin/opengrep
  ```

- ```
  pixi run opengrep --version
  1.30.0
  ```
