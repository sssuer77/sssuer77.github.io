## 1. 项目级别 JDK (Project SDK)
这是 IDEA 管理整个项目的默认 SDK。
路径：File -> Project Structure... -> Project
检查项：
SDK: 确保选中的是 17。
Language level: 确保选中的是 17 (或 "SDK Default")。

<img width="787" height="366" alt="Image" src="https://github.com/user-attachments/assets/0a236f8d-4b29-4b5f-b2ac-8a1c5fc56ac6" />

## 2. 模块级别 JDK (Modules)
有时候子模块会单独设置 JDK，覆盖项目设置。
路径：File -> Project Structure... -> Modules -> 选中你的 backend 模块。
检查项：
Language level: 确保是 17 或 "Project default"。

<img width="1024" height="860" alt="Image" src="https://github.com/user-attachments/assets/d8ee6967-110c-47dc-8348-7debd765c420" />

## 3. Java 编译器版本 (Java Compiler)
这是控制 javac 编译行为的关键点。
路径：File -> Settings -> Build, Execution, Deployment -> Compiler -> Java Compiler
检查项：
Project bytecode version: 设置为 17。
Per-module bytecode version: 下方表格中，确保 backend 模块对应的 Target bytecode version 也是 17（如果为空，它会跟随项目设置）。

<img width="982" height="734" alt="Image" src="https://github.com/user-attachments/assets/11106b5b-9671-48df-a80e-b94f1a2dc38f" />

## 4. Maven 导入环境 (Maven Importing)
IDEA 在解析 pom.xml 时使用的 JDK。
路径：File -> Settings -> Build, Execution, Deployment -> Build Tools -> Maven -> Importing
检查项：
JDK for importer: 建议选择 Project SDK 或明确指定为 17。

<img width="982" height="734" alt="Image" src="https://github.com/user-attachments/assets/f8649c63-c77e-4d51-9581-465ebfa68836" />

## 5. Maven 运行环境 (Maven Runner) —— 【最易忽略，重点检查】
当你点击右侧 Maven 侧边栏的 install 时，IDEA 实际使用的 JDK。
路径：File -> Settings -> Build, Execution, Deployment -> Build Tools -> Maven -> Runner
检查项：
JRE: 不要选 "Default" 或者 "Internal"，请明确选择 17 或 Project SDK。

<img width="982" height="734" alt="Image" src="https://github.com/user-attachments/assets/26e6bd41-19cf-4a4a-b222-8908b96862af" />