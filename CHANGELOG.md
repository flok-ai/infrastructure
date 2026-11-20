# Changelog

All notable changes to this project are documented here. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and versions follow [Semantic Versioning](https://semver.org/).

## [0.1.0] - 2026-11-20

Initial release: Terraform for the platform on Azure, deployed and verified. Every component runs on short-lived, scoped credentials.

### Added

- AKS cluster with networking, shared services (Key Vault, storage, PostgreSQL, registry) and workload identities ([#1](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/1), [#9](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/9)).
- Cilium network policy blocking the cloud metadata endpoint (IMDS) from agent pods ([#10](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/10)).
- Namespaces and other security-relevant values as variables, visible to reviews ([#12](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/12)).
- Cost control: GitHub workflow stopping AKS and PostgreSQL daily and on demand ([#15](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/15)).
- Local development service principal for user delegation SAS testing ([#17](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/17)).
- Key Vault secret initialization and reset scripts ([#21](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/21)).
- Argo Workflows installation with least-privilege RBAC ([#24](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/24)).
- Trusted `foreman` identity for creating runs ([#22](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/22)).
- Per-role agent identities with secret-scoped Key Vault grants, mounted through the CSI driver ([#25](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/25), [#27](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/27)).
- Platform services secrets and database grants ([#30](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/30), [#32](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/32)).
- GitHub token broker infrastructure: App key mount, TokenReview and pod-lookup RBAC, registry push identity ([#37](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/37)).
- Identity diagrams and a verification log of every check run against Azure ([#34](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/34), [#35](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/35), [#40](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/40)).

### Removed

- Shared GitHub token (PAT) from agent secret mounts and Key Vault grants; agents get GitHub tokens from the broker ([#39](https://github.com/julie-ng/ai-native-sdlc-infrastructure/pull/39)).

[0.1.0]: https://github.com/julie-ng/ai-native-sdlc-infrastructure/releases/tag/v0.1.0
