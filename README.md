 paho.mqtt.c 仓库已成功清理，保留了嵌入式 Linux 移植所需的核心内容：

  保留的文件结构

  paho.mqtt.c/
  ├── .git/                          # Git 仓库
  ├── .gitignore                     # Git 忽略规则
  ├── CMakeLists.txt                 # CMake 构建配置
  ├── Makefile                       # Make 构建配置
  ├── version.major/minor/patch     # 版本信息
  ├── cmake/                         # 构建工具（包含 ARM 工具链）
  │   ├── modules/
  │   ├── CPackDebConfig.cmake.in
  │   └── toolchain.linux-arm11.cmake
  ├── src/                           # 源代码 (23,854 行)
  │   ├── samples/                   # 示例代码 (2,911 行)
  │   └── [MQTT 客户端实现文件]
  └── test/                          # 测试代码 (28,175 行)
      └── [C 测试文件]

  删除的内容

  - 文档和许可证：README.md, LICENSE, NOTICE, CODE_OF_CONDUCT.md, CONTRIBUTING.md, PULL_REQUEST_TEMPLATE.md, SECURITY.md, about.html, notice.html, edl-v10,
  epl-v20, doc/, docs/
  - IDE 配置：.cproject, .project, .pydevproject, .settings/, .clang-format
  - CI/CD 配置：.github/, .travis.yml, appveyor.yml, deploy_rsa.enc, build.xml
  - 平台特定代码：android/
  - 不需要的构建文件：cmake-build.sh, cbuild.bat, dist/, test_package/
  - Python 和 SSL 测试：test/python/, test/openssl/, test/ssl/, test/tls-testing/

  验证结果

  - 总大小：15M（已大幅精简）
  - 源代码完整性：所有 MQTT 客户端核心文件保留
  - 构建系统：CMakeLists.txt 和 Makefile 已修复对删除文件的引用
  - 版本信息：version.* 文件完整

  这个精简后的仓库可以直接用于嵌入式 Linux 移植，包含了所有必要的 MQTT 客户端功能、示例代码和测试用例。
