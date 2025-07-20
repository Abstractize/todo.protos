# todo.protos

This repository contains the Protobuf definitions for the **Todo** microservices ecosystem — specifically the analytics domain.

---

## 📁 Repository structure

```
todo.protos/
├── analytics/
│   └── v1/
│       └── task_analytics.proto
├── .gitignore
├── README.md
```

- Organized by domain (`analytics`) and version (`v1`)
- Protobuf packages should follow: `todo.analytics.v1`

---

## 📦 Protobuf package example

```proto
package todo.analytics.v1;

option csharp_namespace = "Analytics.Protos";
option java_package = "com.todo.analytics.grpc";
option java_multiple_files = true;
```

---

## 🚀 Generating code

Use `protoc` to generate client/server stubs in your language of choice.

### Generate Java code

```bash
protoc -I=. --java_out=gen/java analytics/v1/task_analytics.proto
```

### Generate C# code

```bash
protoc -I=. --csharp_out=gen/csharp analytics/v1/task_analytics.proto
```

---

## 🔧 Prerequisites

- Install [Protocol Buffers Compiler (`protoc`)](https://github.com/protocolbuffers/protobuf/releases) and add it to your system PATH.
- If you use gRPC, install the respective language plugin for code generation.
- Optionally, use tools like [Buf](https://buf.build/) to simplify management and validation.

---

## 📌 Notes

- This repo is designed to be consumed as a **Git submodule** or imported directly in your build pipelines.
- Keep protobuf backward compatibility in mind:  
  - Don’t remove or renumber fields.  
  - Use new field numbers for additions.  
- Organize new services and messages by domain and version to avoid conflicts and facilitate evolution.

---

## 📄 .gitignore example

```gitignore
/gen/
/build/
/out/
*.pb.*
.idea/
.vscode/
.DS_Store
```

---

## 💡 Tips

- When cloning this repo with submodules:

```bash
git clone --recurse-submodules https://github.com/your-org/todo.protos.git
```

- Update submodules with:

```bash
git submodule update --remote
```

---

If you want help automating code generation or CI/CD integration, just ask!
