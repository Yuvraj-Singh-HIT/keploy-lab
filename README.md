<div align="center">

<!-- Keploy Logo -->
<img width="654" height="211" alt="image" src="https://github.com/user-attachments/assets/dff2dfed-d2e9-4376-8bc8-ca50f7cbfeff" />

<h1>⚡️ API Tests Faster Than Unit Tests, From User Traffic ⚡️</h1>
<h3>🌟 The Must-Have Tool for Developers in the AI-Gen Era for 90% Test Coverage 🌟</h3>

<!-- Animated Badges -->
<p>
  <a href="https://github.com/keploy/keploy/stargazers">
    <img src="https://img.shields.io/github/stars/keploy/keploy?style=for-the-badge&logo=github&logoColor=white&color=ff69b4" alt="GitHub Stars">
  </a>
  <a href="https://github.com/keploy/keploy/releases">
    <img src="https://img.shields.io/github/v/release/keploy/keploy?style=for-the-badge&logo=go&logoColor=white&color=00ADD8" alt="Latest Release">
  </a>
  <a href="https://github.com/keploy/keploy/blob/main/LICENSE">
    <img src="https://img.shields.io/github/license/keploy/keploy?style=for-the-badge&color=blueviolet" alt="License">
  </a>
  <a href="https://codecov.io/gh/keploy/keploy">
    <img src="https://img.shields.io/codecov/c/github/keploy/keploy?style=for-the-badge&logo=codecov&logoColor=white&color=brightgreen" alt="Coverage">
  </a>
</p>

<p>
  <a href="https://join.slack.com/t/keploy/shared_invite/zt-2dno1yetd-Ec3el~tTwHYIHgGI0jPe7A">
    <img src="https://img.shields.io/badge/Slack-4A154B?style=for-the-badge&logo=slack&logoColor=white" alt="Slack">
  </a>
  <a href="https://www.linkedin.com/company/keploy">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
  </a>
  <a href="https://www.youtube.com/@keploy">
    <img src="https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="YouTube">
  </a>
  <a href="https://twitter.com/Keployio">
    <img src="https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white" alt="X">
  </a>
</p>

<img src="https://raw.githubusercontent.com/keploy/keploy/main/.github/assets/demo.gif" alt="Keploy Demo" width="80%" style="border-radius: 10px; margin: 30px 0;">

</div>

---

## 🚀 What is Keploy?

**Keploy** is a **developer-centric API and integration testing tool** that auto-generates tests and data-mocks **faster than unit tests**. 

It records API calls, database queries, and streaming events — then replays them as tests. Under the hood, Keploy uses **eBPF** to capture traffic at the network layer, making it **completely code-less** and **language-agnostic**.

```bash
# Record real API traffic as tests
keploy record -c "python main.py"

# Replay as deterministic tests
keploy test -c "python main.py" --delay 10
```

<div align="center">

### 🐰 **Fun Fact:** Keploy uses itself for testing! 
[![Coverage Status](https://coveralls.io/repos/github/keploy/keploy/badge.svg?branch=main)](https://coveralls.io/github/keploy/keploy?branch=main)

</div>

---

## ✨ Key Highlights

<table>
<tr>
<td width="50%">

### 🎯 Zero Code Changes

Just run your app with `keploy record`. Real API + integration flows are automatically captured as tests and mocks.

**Powered by eBPF** — No SDKs, no code modifications needed!

</td>
<td width="50%">

### 📹 Record & Replay Complex Flows

Keploy records and replays **complex, distributed API flows** as mocks and stubs.

It's like having a **lightweight time machine** for your tests!

📖 [Read the docs →](https://keploy.io/docs/concepts/record-replay)

</td>
</tr>

<tr>
<td width="50%">

### 🐇 Complete Infra-Virtualization

Unlike tools that only mock HTTP endpoints, Keploy records:

- 💾 **Databases** (Postgres, MySQL, MongoDB)
- 📨 **Message Queues** (Kafka, RabbitMQ)
- 🌐 **External APIs**
- 🔄 **Streaming Events**

Replay them **deterministically** without re-provisioning infra!

📖 [Learn more →](https://keploy.io/docs/concepts/infra-virtualisation)

</td>
<td width="50%">

### 🧪 Combined Test Coverage

**For Developers:** Statement & branch coverage  
**For QA:** API schema & business use-case coverage

Keploy calculates **both** — making coverage objective, not subjective!

📖 [Coverage docs →](https://keploy.io/docs/concepts/coverage)

</td>
</tr>
</table>

### 🤖 AI-Powered Test Expansion

Keploy uses **existing recordings** and **Swagger/OpenAPI schemas** to automatically find:

✅ Boundary values | ✅ Missing/extra fields | ✅ Wrong types | ✅ Out-of-order sequences | ✅ Retries & timeouts

**Expand API Schema, Statement, and Branch Coverage** with AI!

📖 [AI Test Generation →](https://keploy.io/docs/concepts/ai-test-generation)

---

## 🎬 Quick Start

### 1️⃣ Install Keploy Agent

```bash
curl --silent -O -L https://keploy.io/install.sh && source install.sh
```

<details>
<summary>📦 <b>Alternative Installation Methods</b></summary>

<br>

**Using Docker**
```bash
docker pull ghcr.io/keploy/keploy:latest
```

**Direct Binary Download**
```bash
# Linux AMD64
curl -L https://github.com/keploy/keploy/releases/latest/download/keploy_linux_amd64.tar.gz | tar xz

# Linux ARM64
curl -L https://github.com/keploy/keploy/releases/latest/download/keploy_linux_arm64.tar.gz | tar xz

# macOS (Universal)
curl -L https://github.com/keploy/keploy/releases/latest/download/keploy_darwin_all.tar.gz | tar xz
```

**Using Homebrew (macOS)**
```bash
brew install keploy
```

**No Root Installation**
```bash
curl --silent -O -L https://keploy.io/install.sh && source install.sh -noRoot
```

</details>

### 2️⃣ Record Test Cases

Start your app under Keploy to convert **real API calls** into tests and mocks:

```bash
keploy record -c "CMD_TO_RUN_APP"
```

**Examples:**

| Language | Command |
|----------|---------|
| 🐍 **Python** | `keploy record -c "python main.py"` |
| 📜 **Node.js** | `keploy record -c "node app.js"` |
| 🔵 **Go** | `keploy record -c "./app"` |
| ☕ **Java** | `keploy record -c "java -jar app.jar"` |
| 🐳 **Docker** | `keploy record -c "docker-compose up"` |
| 💎 **Ruby** | `keploy record -c "ruby app.rb"` |

### 3️⃣ Run Tests

Run tests **offline** without external dependencies:

```bash
keploy test -c "CMD_TO_RUN_APP" --delay 10
```

---

## 🛠️ Other Capabilities

| Feature | Description |
|---------|-------------|
| 🌐 **CI/CD Integration** | Run tests with mocks in Jenkins, GitHub Actions, GitLab CI, or Kubernetes clusters |
| 🎭 **Multi-Purpose Mocks** | Use Keploy-generated mocks as server tests |
| 📊 **Unified Reporting** | API, integration, unit, and e2e coverage with CI/PR insights |
| 🖥️ **Developer Console** | View, manage, and debug recorded tests and mocks |
| ⏱️ **Time Freezing** | Deterministic test replay by freezing system time ([Learn more](https://keploy.io/docs/concepts/time-freezing)) |
| 📚 **Mock Registry** | Centralized registry to manage, reuse, and version mocks ([Learn more](https://keploy.io/docs/concepts/mock-registry)) |

---

## 🌍 Works With Any Language & Framework

Because Keploy intercepts at the **network layer (eBPF)**, it works with **any language, framework, or runtime** — no SDK required!

<div align="center">

<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript">
<img src="https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white" alt="Go">
<img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java">
<img src="https://img.shields.io/badge/Ruby-CC342D?style=for-the-badge&logo=ruby&logoColor=white" alt="Ruby">
<img src="https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white" alt="PHP">
<img src="https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white" alt="Rust">
<img src="https://img.shields.io/badge/.NET-512BD4?style=for-the-badge&logo=dotnet&logoColor=white" alt=".NET">

<br><br>

<img src="https://img.shields.io/badge/Express.js-404D59?style=for-the-badge&logo=express&logoColor=white" alt="Express">
<img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI">
<img src="https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white" alt="Django">
<img src="https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white" alt="Spring">
<img src="https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white" alt="Flask">
<img src="https://img.shields.io/badge/Gin-00ADD8?style=for-the-badge&logo=go&logoColor=white" alt="Gin">

</div>

> **Note:** Some dependencies are not open-source by nature because their protocols and parsings are not open-sourced. These are not supported in Keploy Enterprise.

---

## 📚 Resources & Community

<table>
<tr>
<td width="50%">

### 📖 Documentation
- [📘 Getting Started](https://keploy.io/docs/getting-started)
- [🏁 Quick Start Guides](https://keploy.io/docs/quickstart)
- [🔧 API Reference](https://keploy.io/docs/api-reference)
- [💡 Concepts](https://keploy.io/docs/concepts)
- [🎓 Tutorials](https://keploy.io/docs/tutorials)

</td>
<td width="50%">

### 🤝 Community & Support
- [💬 Join Slack](https://join.slack.com/t/keploy/shared_invite/zt-2dno1yetd-Ec3el~tTwHYIHgGI0jPe7A)
- [📢 Blog & Updates](https://keploy.io/blog)
- [🐛 Report Issues](https://github.com/keploy/keploy/issues)
- [💡 Feature Requests](https://github.com/keploy/keploy/discussions)
- [🎥 YouTube Tutorials](https://www.youtube.com/@keploy)

</td>
</tr>
</table>

---

## 🚀 Need Help Getting Started?

<div align="center">

### 📞 Book a Live Demo / Enterprise Support

Want a **guided walkthrough**, **dedicated support**, or help planning **enterprise rollout**?

[![Email](https://img.shields.io/badge/Email-sales@keploy.io-blue?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sales@keploy.io)
[![Calendar](https://img.shields.io/badge/Schedule-A_Meeting-green?style=for-the-badge&logo=google-calendar&logoColor=white)](https://calendly.com/keploy)

*Prefer a calendar invite? Mention your availability in the email — we'll send one right away!*

</div>

---

## 🤝 Contributing

We ❤️ contributions! Keploy is built by the community, for the community.

<div align="center">

[![Contributors](https://contrib.rocks/image?repo=keploy/keploy)](https://github.com/keploy/keploy/graphs/contributors)

</div>

### How to Contribute

1. 🍴 **Fork** the repository
2. 🌿 **Create** your feature branch (`git checkout -b feature/AmazingFeature`)
3. 💾 **Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. 📤 **Push** to the branch (`git push origin feature/AmazingFeature`)
5. 🔀 **Open** a Pull Request

📜 Read our [Contribution Guidelines](CONTRIBUTING.md) and [Code of Conduct](CODE_OF_CONDUCT.md) before contributing.

---

## 📊 Project Stats

<div align="center">

![GitHub Activity](https://img.shields.io/github/commit-activity/m/keploy/keploy?style=flat-square&color=brightgreen)
![GitHub Issues](https://img.shields.io/github/issues/keploy/keploy?style=flat-square&color=orange)
![GitHub Pull Requests](https://img.shields.io/github/issues-pr/keploy/keploy?style=flat-square&color=blue)
![GitHub Last Commit](https://img.shields.io/github/last-commit/keploy/keploy?style=flat-square&color=red)

</div>

---

## 🏆 Recognition

<div align="center">

<a href="https://landscape.cncf.io/?selected=keploy">
  <img src="https://raw.githubusercontent.com/cncf/artwork/master/other/cncf-landscape/horizontal/color/cncf-landscape-horizontal-color.svg" width="300px" alt="CNCF Landscape">
</a>

**Keploy is proud to be part of the CNCF Landscape!**

</div>

---

## ⭐ Star History

<div align="center">

<a href="https://star-history.com/#keploy/keploy&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=keploy/keploy&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=keploy/keploy&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=keploy/keploy&type=Date" width="100%"/>
  </picture>
</a>

</div>

---

## 📄 License

Keploy is licensed under the [Apache License 2.0](LICENSE).

---

<div align="center">

### Made with ❤️ by the Keploy Community

<a href="https://github.com/keploy/keploy">
  <img src="https://img.shields.io/badge/⭐_Star_Us_On_GitHub-Help_us_reach_20k_stars!-yellow?style=for-the-badge" alt="Star us on GitHub">
</a>

</div>
