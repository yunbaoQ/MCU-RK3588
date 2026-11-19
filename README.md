# MCU 与 RK3588 嵌入式学习记录

学习平台：WSL2、RK3588，后续加入 STM32 / FreeRTOS。

## 目录

- `src/`：C/C++ 源代码。
- `tests/`：后续测试程序与测试数据。
- `docs/`：后续学习与开发说明。
- `build/`：本地编译产物，不提交到 Git。
- `wsl2-gdb.txt`：电脑开发工具版本记录。
- `rk3588-config.txt`：RK3588 系统和硬件信息记录。

## 在 WSL Linux 中编译运行

在本仓库根目录执行：

```bash
mkdir -p build
gcc -std=c11 -Wall -Wextra -Wpedantic -g -O0 src/hello.c -o build/hello
./build/hello
```

当前 `hello.c` 保留了未使用变量 `a`，用于观察编译警告；修复练习时可删除该变量并重新编译。

此命令生成的是当前 Linux 主机架构的程序，不是 STM32 固件。部署到 RK3588 时需在板上编译，或使用适合目标系统的交叉工具链。
