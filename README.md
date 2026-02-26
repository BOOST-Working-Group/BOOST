# Biomass Open Origin Standard for Tracking (BOOST) Community Group

## ⚠️ Critical Documentation Architecture Notice

**This repository uses a sophisticated HYBRID documentation system (Bikeshed + ReSpec layout)**

🚫 **DO NOT** "simplify" or "clean up" the build system without reading [`ARCHITECTURE.md`](ARCHITECTURE.md)  
🚫 **DO NOT** remove ReSpec-style components thinking they're "inappropriate for Bikeshed"  
🚫 **DO NOT** remove the Python HTML processing in `build.sh`  

✅ **This is intentional design** - See commit `v3.1.3-5-g725c24a` for reference implementation

---

[![Build & Deploy Documentation](https://github.com/BOOST-Working-Group/BOOST/workflows/🚀%20Build%20&%20Deploy%20Documentation/badge.svg)](https://github.com/BOOST-Working-Group/BOOST/actions/workflows/build-deploy.yml)
[![Schema Validation](https://github.com/BOOST-Working-Group/BOOST/workflows/🔍%20Schema%20Validation/badge.svg)](https://github.com/BOOST-Working-Group/BOOST/actions/workflows/schema-validation.yml)
[![PR Validation](https://github.com/BOOST-Working-Group/BOOST/workflows/📋%20PR%20Validation/badge.svg)](https://github.com/BOOST-Working-Group/BOOST/actions/workflows/validate-pr.yml)
[![Development Docs](https://github.com/BOOST-Working-Group/BOOST/workflows/📚%20Build%20Development%20Documentation/badge.svg)](https://github.com/BOOST-Working-Group/BOOST/actions/workflows/build-dev-docs.yml)

## Overview
This repository contains the working draft and artifacts of the Biomass Open Origin Standard for Tracking (BOOST), which defines a robust and interoperable data model for tracking biomass through complex supply chains. The standard supports transparent, verifiable, and consistent data exchange to enable sustainability, regulatory compliance, and supply chain integrity.

**Current Version: {{VERSION}}** - Enhanced collaboration with GitHub Issues-based enhancement planning, build system improvements, and comprehensive documentation consistency validation.

- **Charter:** [BOOST_Charter.org](BOOST_Charter.org)
- **Charter Effective Date:** 
- **Last Modified:** 

Feedback and contributions are welcomed via GitHub Issues and Pull Requests at [BOOST](https://github.com/BOOST-Working-Group/BOOST).

W3C Community Group page: [BOOST-01](https://www.w3.org/community/boost-01/)

## 📋 Documentation Access

### **Primary Documentation**
- **[📄 Complete PDF Specification](https://BOOST-Working-Group.github.io/BOOST/boost-spec.pdf)** - 88+ page comprehensive specification with all 36 entities
- **[🌐 Interactive HTML Specification](https://BOOST-Working-Group.github.io/BOOST/boost-spec.html)** - W3C-compliant browsable documentation
- **[📊 Interactive ERD Navigator](https://BOOST-Working-Group.github.io/BOOST/erd-navigator/)** - Visual exploration of entity relationships and data model
- **[🗂️ JSON Schema Repository](https://github.com/BOOST-Working-Group/BOOST/tree/main/drafts/current/schema)** - 36 validation schemas (single source of truth)

### **Development Resources**
- **[📈 Build and Consistency Reports](https://github.com/BOOST-Working-Group/BOOST/tree/main/drafts/current/specifications/build)** - Automated validation and generation statistics
- **[📝 Complete Version History](https://github.com/BOOST-Working-Group/BOOST/blob/main/CHANGELOG.md)** - Detailed change documentation
- **[✅ Enhancement Planning](https://github.com/BOOST-Working-Group/BOOST/issues?q=label%3Aplan)** - GitHub Issues-based project planning with stakeholder collaboration

## 🚀 Recent Changes & Improvements

### **Latest Updates (v3.4.2)**
- **📋 Enhanced Collaboration**: Migrated all enhancement plans to GitHub Issues ([#259](https://github.com/BOOST-Working-Group/BOOST/issues/259)-[#262](https://github.com/BOOST-Working-Group/BOOST/issues/262)) for improved stakeholder engagement and transparency
- **🔧 Build System Refinements**: Resolved HTML generation consistency issues and header formatting problems
- **🧹 Documentation Organization**: Streamlined planning documents and improved developer experience
- **📝 Stakeholder Materials**: Comprehensive interagency presentation materials for California agency engagement

### **Major Release Features (v3.4.x Series)**
- **🎯 Distributed Tolerance Framework**: Equipment accuracy, process loss, and regulatory compliance tolerances distributed across entities where they physically manifest
- **📍 Enhanced Tracking Points System**: 7-point tracking system with consolidation_point replacement for deprecated skid_road/forest_road concepts
- **🐍 Complete Python Validation**: Full validate_all() function with six validation categories, process-specific tolerances, and automated recommendations
- **🔧 Schema Integrity Enhancements**: Comprehensive cross-entity validation, array foreign key patterns, and quality grade standardization
- **📊 Complete Entity Coverage**: All 36 entities documented with enhanced IdentificationMethod integration and documentation consistency

### **Current System Status**
- ✅ **Entity Coverage**: 36/36 entities documented with complete JSON Schema validation
- ✅ **Build System**: Unified single-command build process with HTML/PDF generation
- ✅ **Documentation Consistency**: 100% cross-format validation between PDF and HTML outputs
- ✅ **Version Management**: Automatic git tag-based versioning with complete traceability
- ✅ **CI/CD Integration**: Automated quality gates with comprehensive testing and deployment
- ✅ **Community Engagement**: GitHub Issues-based enhancement planning with stakeholder collaboration

## 🌟 Key Features

### BOOST Traceability System Implementation
- **Media-Interruption-Free Traceability** - TraceableUnit (TRU) entities with biometric identification
- **Three Critical Tracking Points** - harvest_site, skid_road, forest_road, mill_entrance infrastructure
- **Multi-Species Support** - Species-specific tracking within mixed material flows
- **Complete Processing Chain** - MaterialProcessing with input/output TRU relationships

### Plant Part Categorization System
- **17 Standardized Plant Parts** - trunk, heartwood, sapwood, bark, branches, leaves, seeds, etc.
- **Processing Transformations** - Detailed tracking of plant part changes during operations
- **Value Optimization** - Route materials based on plant part composition
- **Circular Economy** - Byproduct and waste stream management

### Enhanced Geographic Integration
- **GeoJSON Compliance** - Spatial data support for all location-aware entities
- **California Agency Ready** - Administrative boundary and jurisdiction tracking
- **Supply Base Management** - Infrastructure mapping with harvest sites and transportation routes

### Comprehensive Entity System
- **35 Interconnected Entities** - Complete data model covering all aspects of biomass supply chains across 7 thematic areas
- **JSON-LD Validation** - Structured schemas with business rules and examples
- **Interactive ERD Navigator** - Dynamic exploration with GitHub discussion integration
- **Sustainability Claims** - Species-specific claims with inheritance through processing

## 📁 Directory Structure

```
.
├── README.md                # This file
├── LICENSE.md               # License info (not auto-created)
├── CODE_OF_CONDUCT.md       # Community standards (not auto-created)
├── CONTRIBUTING.md          # Contribution guide (not auto-created)
├── BOOST_Charter.org        # Group charter (not auto-created)
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   └── feature_request.md
│   ├── workflows/           # Automated CI/CD workflows
│   │   ├── release.yml              # Release automation for all semantic versions
│   │   ├── build-deploy.yml         # Development builds and GitHub Pages deployment  
│   │   ├── version-check.yml        # Version analysis and guidance
│   │   └── docker-image.yml         # Container image maintenance
│   └── WORKFLOWS.md         # Comprehensive workflow documentation
├── erd-navigator/           # Interactive ERD Navigator for stakeholder feedback
│   ├── index.html                   # Main interactive ERD interface
│   └── README.md                    # Navigator documentation
├── drafts/                  # Organized draft content
│   ├── current/             # Active working content
│   │   ├── specifications/        # Current spec documents
│   │   ├── schema/               # Entity schemas and validation (36 entities)
│   │   │   ├── traceable_unit/        # Core TRU entity with examples
│   │   │   ├── species_component/     # Multi-species tracking
│   │   │   ├── material_processing/   # Processing operations
│   │   │   └── [32 additional entities] # Complete BOOST Traceability System
│   │   ├── images/
│   │   │   ├── current/              # Interactive ERD and current visuals
│   │   │   └── archive/              # Historical ERD iterations and deprecated files
│   │   ├── examples/             # Sample payloads and validation
│   │   └── communications/       # Agency outreach materials
│   ├── archive/             # Historical content
│   │   ├── v1_drafts/            # Early specification drafts
│   │   ├── working_notes/        # Development notes (.org files)
│   │   └── deprecated_schemas/   # Old schema versions
│   └── tools/               # Development utilities
├── proposals/
├── meetings/
│   └── templates/
├── use-cases/
├── presentations/
├── tools/
├── data/                    # Optional: Sample or test data
├── tests/                   # Integration testing scenarios
│   └── BOOST_INTEGRATION_TESTING_SCENARIOS.md
└── drafts/current/specifications/  # Technical specifications and migration guides
    └── MATERIALBATCH_TO_TRU_MIGRATION_GUIDE.md
```

## 📂 Purpose of Each Directory

- `drafts/`: Organized draft content with clear current vs. archive separation
  - `current/`: Active working specifications, schemas, examples, and communications
  - `archive/`: Historical content preserved for reference
  - `tools/`: Development utilities for schema generation and validation
- `proposals/`: Early-stage ideas and design sketches
- `meetings/`: Agendas, minutes, and templates
- `use-cases/`: User scenarios guiding spec design
- `presentations/`: Slides and visual materials
- `tests/`: Integration testing scenarios for BOOST Traceability System validation
- `drafts/current/specifications/`: Technical specifications and migration guides

## 🚀 Getting Started

### For Developers
1. **Explore the Interactive ERD**: Use the [Interactive ERD Navigator](erd-navigator/index.html) to explore all 36 entities with dynamic filtering and GitHub discussion integration
2. **Review Entity Schemas**: Check `drafts/current/schema/` for JSON validation schemas and examples
3. **Review Schema Organization**: Check entity schemas in `drafts/current/schema/` for implementation details
4. **Migration Guide**: See `drafts/current/specifications/MATERIALBATCH_TO_TRU_MIGRATION_GUIDE.md` for conceptual changes

### For Standards Organizations
- **California Agencies**: GeoJSON spatial data ready for regulatory integration
- **Certification Bodies**: Multi-scheme support with claim inheritance
- **Supply Chain Partners**: TRU-centric design for seamless data exchange

### For Implementation Testing
- **Integration Scenarios**: See `tests/BOOST_INTEGRATION_TESTING_SCENARIOS.md`
- **Plant Part Examples**: Review processing transformations in `drafts/current/schema/material_processing/`
- **Multi-Species Cases**: Check species component tracking in `drafts/current/schema/species_component/`
- **Transaction Examples**: See `drafts/current/examples/transactions/`

## 🎯 Interactive ERD Navigator

The [Interactive ERD Navigator](erd-navigator/index.html) provides a comprehensive, stakeholder-friendly way to explore the BOOST data model:

### 🔍 Key Features
- **35 Entity Coverage**: Complete visualization of all entities across 7 thematic areas
- **Dynamic Filtering**: Focus on specific domains (Core Traceability, Organizational, Material & Supply, etc.)
- **Direct Discussion Access**: Purple 💬 icons in each entity header link directly to GitHub discussions
- **TraceableUnit Focus Mode**: 🎯 button to reduce visual complexity and highlight essential relationships
- **Schema Integration**: Real-time loading of entity definitions from JSON schema files

### 🎨 Thematic Organization
- 🟢 **Core Traceability** (9 entities): TraceableUnit, MaterialProcessing, DataReconciliation, etc.
- 🔵 **Organizational** (4 entities): Organization, Certificate, CertificationScheme, CertificationBody
- 🟤 **Material & Supply** (4 entities): Material, SupplyBase, Supplier, Customer
- 🟠 **Transactions** (3 entities): Transaction, TransactionBatch, SalesDeliveryDocument
- 🟡 **Sustainability** (1 entity): Claim
- 🟣 **Geographic** (1 entity): GeographicData
- 🔴 **Reporting** (3 entities): SupplyBaseReport, VerificationStatement, Audit
- ⚫ **Analytics** (2 entities): EnergyCarbonData, MoistureContent
- 👥 **Personnel** (2 entities): Operator, ProductGroup

### 💬 Community Feedback
Each entity has a dedicated GitHub discussion thread accessible via the ERD. This enables:
- **Structured feedback** on schema definitions and relationships
- **Real-world validation** from supply chain stakeholders
- **Iterative improvement** based on implementation experience

**Access**: Visit the [Live Interactive ERD Navigator](https://BOOST-Working-Group.github.io/BOOST/erd-navigator/) or use the local version at `erd-navigator/index.html`

## 📊 Current Status

- **✅ Complete**: BOOST Traceability System Phases 1-3 implementation
- **✅ Complete**: Plant part categorization system 
- **✅ Complete**: 36 entity schemas with validation and examples
- **✅ Complete**: Interactive ERD Navigator with GitHub discussion integration
- **✅ Complete**: Integration testing scenarios and migration documentation
- **🔄 Active**: Community feedback integration and use case expansion

## 🏷️ Version Nomenclature

BOOST uses Git-based semantic versioning with development build identification. Understanding the version format is essential for tracking releases and development progress.

### Version Format: `vX.Y.Z-N-gHHHHHHH`

All BOOST versions follow the **Git describe** format, providing precise traceability:

#### **Components Breakdown:**

1. **`vX.Y.Z`** - **Base Release Tag**
   - Latest official release using semantic versioning (Major.Minor.Patch)
   - Example: `v3.4.2` represents a patch release in the 3.4.x series

2. **`-N`** - **Commits Since Release** 
   - Number of commits made since the base release tag
   - Indicates this is a **development build**, not an official release
   - Higher numbers = more development activity since last release

3. **`-g`** - **Git Indicator**
   - Standard Git convention indicating the following is a commit hash
   - The "g" stands for "git"

4. **`HHHHHHH`** - **Commit Hash (Short)**
   - 7-character abbreviated SHA hash of the specific commit
   - Uniquely identifies the exact code state used for this build
   - Full hash is longer but abbreviated for readability

### **Version Types:**

| Format | Type | Description | Example |
|--------|------|-------------|---------|
| `vX.Y.Z` | **Release** | Official tagged release | Stable, production-ready |
| `vX.Y.Z-N-gHHHHHHH` | **Development** | N commits after release | In-progress development |
| `vX.Y.Z-1-gHHHHHHH` | **Post-Release** | 1 commit after new release | Latest development |

### **Development Build Evolution:**

```
vX.Y.Z           ← Official release (tagged)
vX.Y.Z-1-gHHHHHHH ← 1 commit after release  
vX.Y.Z-2-gHHHHHHH ← 2 commits after release
vX.Y.Z-3-gHHHHHHH ← 3 commits after release
vX.Y.Z-4-gHHHHHHH ← 4 commits after release  
vX.Y.Z-5-gHHHHHHH ← 5 commits after release
```

### **Practical Usage:**

- **🎯 Exact Reproduction**: Any version can be reproduced with `git checkout <commit-hash>`
- **📋 Issue Reporting**: Always include full version for accurate debugging
- **🚀 Release Planning**: Development versions show progress toward next release
- **🔍 Build Tracking**: CI/CD systems use this for automated version management

### **In Documentation Builds:**

- **HTML/PDF Headers**: Show exact version used for generation
- **Build Logs**: Include version for reproducibility tracking  
- **Release Artifacts**: Tagged with precise version information
- **GitHub Actions**: Automatically extract and use for build naming

This versioning system ensures **complete traceability** - you can always identify the exact code state that generated any documentation build or release artifact.

## 🤖 Automated CI/CD Workflows

The BOOST repository includes comprehensive GitHub Actions automation for documentation building, validation, and release management.

### Key Features
- **🐳 Docker Containerization**: All builds use pre-built containers for 4-6x faster execution
- **🚀 Automatic Releases**: Every semantic version tag triggers complete release packages
- **✅ Schema Validation**: Comprehensive validation of all 36 entity schemas
- **📄 Multi-Format Output**: HTML, PDF, and interactive ERD Navigator generation

### Workflow Overview

| Workflow | Trigger | Purpose | Performance |
|----------|---------|---------|------------|
| **Release Documentation** | Version tags (`v*.*.*`) | Build & publish releases | ~3-4 min |
| **Build Documentation** | Branch pushes | Development builds + Pages deploy | ~2-3 min |
| **Version Management** | Version tags | Version analysis & guidance | ~5 sec |
| **Docker Image Builder** | Dockerfile changes | Container maintenance | ~5-8 min |

### Quick Start

#### Create a Release
```bash
# Any semantic version automatically triggers release
git tag vX.Y.Z
git push origin vX.Y.Z

# This automatically:
# 1. Builds complete documentation (HTML + PDF)
# 2. Validates all schemas and relationships
# 3. Creates GitHub release with downloadable packages
# 4. Updates documentation website
```

#### Development Workflow
```bash
# Push to any branch triggers development build
git push origin feature/new-entity

# For main branch pushes, also updates:
# - https://BOOST-Working-Group.github.io/BOOST/
# - Interactive ERD Navigator
# - Schema file access
```

### Performance Improvements
- **Before Docker**: 8-10 minute builds with dependency installation
- **After Docker**: 2-4 minute builds using pre-built containers
- **Reliability**: Eliminated dependency installation failures
- **Consistency**: Same environment for all builds

📖 **Full Documentation**: See [.github/WORKFLOWS.md](.github/WORKFLOWS.md) for comprehensive workflow documentation, troubleshooting guides, and maintenance procedures.

## 🔧 Development Tools

### Schema Integrity Reviewer Sub-Agent

The repository includes a comprehensive schema integrity validation tool at `tools/agents/schema-integrity-reviewer.md`. This Claude Code sub-agent performs systematic validation of the BOOST schema system.

#### Setup Instructions

**Option 1 - Automatic Discovery (Recommended)**:
Claude Code should automatically discover the agent from the `tools/agents/` directory when running from the repository root.

**Option 2 - Manual Registration**:
If automatic discovery doesn't work, copy the agent to your local Claude directory:
```bash
mkdir -p ~/.claude/agents
cp tools/agents/schema-integrity-reviewer.md ~/.claude/agents/
```

**Option 3 - Direct Reference**:
Use the Task tool to reference the agent file directly from `tools/agents/schema-integrity-reviewer.md`.

#### Usage

Once configured, invoke the agent in Claude Code:
```
schema-integrity-reviewer
```

#### Key Capabilities

- **Orphaned Foreign Key Detection**: Identifies broken references and missing entities
- **Data Model Design Validation**: Catches normalization violations and data duplication  
- **Multi-System Alignment**: Ensures consistency between schemas, ERD config, and validation rules
- **Python Implementation Testing**: Validates that the reference implementation stays synchronized
- **Pattern Standardization**: Verifies consistent ID patterns and naming conventions
- **Comprehensive Reporting**: Provides specific file locations and actionable fixes

#### When to Use

- After modifying any JSON schema files
- Before creating pull requests with schema changes
- When adding new entities or relationships
- During troubleshooting of validation errors
- As part of regular schema maintenance

See `tools/agents/README.md` for detailed setup instructions and troubleshooting.

## 🚀 Contributing

Please review `CONTRIBUTING.md` and our `CODE_OF_CONDUCT.md` before submitting PRs or issues.

For technical discussions about the BOOST Traceability System implementation or plant part categorization, please use GitHub Issues with appropriate labels.

