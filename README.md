# Afrowave Community Web Apps

Welcome to the **Afrowave Community Web Apps** repository. This solution forms the *primary application layer* of the Afrowave ecosystem: the place where user-facing web services, orchestration services, authentication gateways, and management dashboards come together.

This repository is intentionally structured as a **modular, multi‑project web application suite**, designed to support the Afrowave identity, education, translation, and community platforms.

---

## 🎯 Purpose of This Repository
This repo hosts all server‑side and web‑based components of the Afrowave Community. It is the **application layer** sitting above Afrowave.SharedTools and Afrowave.Localization. Its tasks include:

- Providing cohesive web access to Afrowave services.
- Hosting central orchestration services (Hub, Network Manager).
- Offering authentication and identity mapping.
- Delivering portals for teachers, students, and administrators.
- Enabling distributed, secure server discovery and coordination.

This is where Afrowave shifts from libraries and engines… to real applications.

---

## 📦 High‑Level Architecture
The architecture is designed around several principles:

- **Modularity**: Each app has a focused responsibility.
- **Shared foundations**: All apps depend on `Afrowave.SharedTools` for models, helpers, and contracts.
- **Internal consistency**: Unified API responses, settings, and naming conventions.
- **Scalability**: Designed for a multi‑server, multi‑region environment.
- **Identity‑centric**: User identity is based on email or AD domain identity, seamlessly mapped through the Auth API.

---

## 🧩 Projects Inside This Repository
The solution begins empty and grows by adding clear, independent projects. Expected components include:

### **1. Afrowave.Hub**
The central orchestrator of the Afrowave application layer.
- Minimal API (ASP.NET 10)
- Server heartbeat / server registration
- Distribution of active server lists
- Coordination for distributed services
- SignalR events for real‑time updates

### **2. Afrowave.NetworkManager**
A web UI and service layer responsible for monitoring networked Afrowave nodes.
- Displays active servers and their roles
- Integration with WireGuard client/server presence (later phase)
- REST endpoints for diagnostics
- Designed as a companion to Hub

### **3. Afrowave.AuthApi**
Authentication and identity mapping service for the entire Afrowave platform.
- Login via email prefix or full address
- Domain account mapping (Samba AD / Kerberos)
- Token issuance for web and desktop clients
- Central user identity resolver

### **4. Afrowave.CommunityPortal**
The public-facing portion of Afrowave.
- Teacher dashboards
- Student tools
- Future community features
- Will use Blazor Server or Razor Pages

### **5. Afrowave.Web.Shared**
A shared project containing:
- Middleware
- UI helpers
- Common attributes
- Shared service interfaces
- Any non-library utilities intended purely for the web layer

---

## 🔗 Dependency: Afrowave.SharedTools
All projects depend on `Afrowave.SharedTools`, which provides:

- Unified API response types (`ApiResponse<T>`, error structures).
- Shared models for identity, servers, apps, and networking.
- Helpers, tools, and common abstractions.

This ensures that all Afrowave applications speak the same internal language.

---

## 🧬 Core Models Used Across This Repo
While detailed models live in `SharedTools`, the following categories are central to this repository's operation:

### **Identity & Authentication Models**
- `UserIdentity`
- `UserEmailIdentifier`
- `DomainUserReference`
- `SessionValidationResult`

### **Server & Network Models**
- `ServerInfo`
- `ServerRole`
- `ServerStatus`
- `ActiveServerList`

### **Application Models**
- `AppMetadata`
- `AppRegistration`
- `ClientDeviceType`
- `ClientCapability`

### **Utility Models**
- `TimestampedValue<T>`
- `ChangeSet<T>`
- `TrackingState`

---

## 🚀 Development Strategy
Afrowave applications are built step by step. The workflow is:

1. **Define new models** inside `SharedTools` first.
2. **Publish a SharedTools NuGet package**.
3. **Consume the updated package** here in the web apps.
4. **Add new projects** as needed, keeping each focused and small.
5. **Write documentation concurrently**, keeping everything discoverable.

This ensures that the architecture remains predictable and maintainable.

---

## 🧭 Roadmap
### **Phase 1: Foundations**
- Create blank solution and project structure.
- Add SharedTools dependency.
- Implement Hub minimal API skeleton.
- Implement AuthApi basic login flow.

### **Phase 2: Network Layer**
- Add NetworkManager UI.
- Connect to Hub orchestration.
- Add server heartbeat + registration.

### **Phase 3: Community Portal**
- Build teacher/student dashboards.
- Integrate translation and localization services.
- Add real‑time classroom tools.

### **Phase 4: Advanced Services**
- Full server auto‑discovery.
- Real‑time events via SignalR.
- Integration with Afrowave Localization Dispatcher.

---

## 🛠 Contribution Philosophy
Afrowave is built on clarity, modularity, and education. Each commit should:
- Keep projects focused.
- Prefer explicitness over magic.
- Improve readability and structure.
- Expand documentation when adding new features.

This repo is both a production project *and* a teaching tool for the Afrowave community.

---

## 📄 License
To be added after the initial architectural pass.

---

## 💬 Contact & Community
This repository is part of the wider **Afrowave ecosystem** – a collection of educational, infrastructure, and tooling projects designed to empower learners and developers globally.

More modules, documentation, and starter projects will be added soon.

