# 🚀 CI/CD Overview

The BookVerse Recommendations Service implements a sophisticated, enterprise-grade CI/CD pipeline that demonstrates modern software delivery practices with comprehensive automation, security, and compliance.

## 🎯 Pipeline Highlights

### Core Capabilities
- **🔄 Intelligent Commit Analysis** - Smart filtering for application version creation
- **🏗️ Multi-Artifact Building** - Coordinated building of 4 distinct artifacts
- **🛡️ Comprehensive Security** - OIDC authentication and evidence-based compliance
- **📊 Complete Traceability** - Full artifact lineage and build provenance
- **🚀 Automated Promotion** - End-to-end deployment through 4 stages

### Artifacts Produced
1. **📱 API Docker Image** - Main recommendation service
2. **🔧 Worker Docker Image** - Background processing service
3. **⚙️ Configuration Bundle** - Algorithm parameters and settings
4. **📚 Resources Bundle** - ML models and training data

### Security & Compliance
- **OIDC Authentication** - No long-lived tokens or stored credentials
- **Evidence Collection** - 6 different evidence types at package and application levels
- **Security Scanning** - SAST, dependency scanning, and vulnerability assessment
- **Compliance Gates** - Automated policy enforcement at each stage

### Deployment Pipeline
```
📝 Commit → 🔍 Analysis → 🏗️ Build → 📦 Publish → 
🛡️ Evidence → 📋 App Version → 🧪 DEV → 🔍 QA → 🏗️ STAGING → 🚀 PROD
```

## 📚 Comprehensive Documentation

For detailed information, see our extensive documentation suite:

- **[CI/CD Architecture](./CI_CD_ARCHITECTURE.md)** - Complete system design and architecture
- **[Workflow Reference](./WORKFLOW_REFERENCE.md)** - Step-by-step workflow breakdown and troubleshooting
- **[Troubleshooting Guide](./TROUBLESHOOTING.md)** - Common issues and solutions
- **[Implementation Plan](./CI_CD_PLAN.md)** - Detailed development strategy

## 🚀 Quick Start

### Prerequisites
```yaml
# Repository Variables
PROJECT_KEY: "bookverse"
JFROG_URL: "https://apptrusttraining1.jfrog.io"
DOCKER_REGISTRY: "apptrusttraining1.jfrog.io"
EVIDENCE_KEY_ALIAS: "bookverse-signing-key"

# Repository Secrets
EVIDENCE_PRIVATE_KEY: "[PEM formatted private key]"
```

### Trigger Pipeline
```bash
# Automatic trigger
git push origin main

# Manual trigger with debugging
gh workflow run ci.yml -f reason="Testing new feature" -f force_app_version=true
```

### Monitor Progress
```bash
# View latest run
gh run list --workflow=ci.yml --limit=1

# Follow logs in real-time
gh run watch
```

This pipeline represents a production-ready implementation suitable for enterprise environments while maintaining clarity for demonstration purposes.
