# BOOST Interactive ERD Navigator

This directory contains the interactive Entity Relationship Diagram navigator for stakeholder feedback on the BOOST data standard.

## Purpose

The Interactive ERD Navigator provides a comprehensive interface for stakeholders to:
- **Explore** the complete BOOST data model with 36 entities across 7 thematic areas
- **Navigate** directly to GitHub discussions via purple chat icons in each entity
- **Filter** entities by thematic areas (Core Traceability, Organizational, Material & Supply, etc.)
- **Provide feedback** without requiring deep technical knowledge of GitHub or version control

## Features

### 🎯 Interactive Exploration
- **Zoom & Pan**: Mouse wheel zoom, click-and-drag panning for detailed exploration
- **Smart Filtering**: 9 thematic filter buttons to focus on specific domain areas
- **TraceableUnit Focus Mode**: 🎯 button to highlight only essential relationships, reducing visual clutter
- **Dynamic Labels**: Toggle relationship labels on/off for cleaner viewing

### 💬 Direct Discussion Access
- **Purple Chat Icons**: Each entity header has a 💬 icon linking directly to its GitHub discussion
- **Complete Coverage**: All 36 entities have dedicated discussion threads
- **Schema Integration**: Discussions include complete field definitions and validation requirements

### 🏗️ Advanced Visualization
- **Dynamic Schema Loading**: Entity definitions loaded from JSON schema files
- **Field Type Legend**: Clear indication of Primary Keys (PK), Foreign Keys (FK), Required/Optional fields
- **Relationship Highlighting**: Click relationships to see focus information
- **Professional Styling**: Clean, GitHub-style design with responsive layout

## Structure

- `index.html` - Complete interactive ERD with embedded functionality
- Integrates directly with schema files in `../drafts/current/schema/`
- Links to 36 entity-specific GitHub Discussions

## Entity Coverage (36 Total)

### 🟢 Core Traceability (10 entities)
TraceableUnit, MaterialProcessing, ProcessingHistory, SpeciesComponent, MeasurementRecord, LocationHistory, BiometricIdentifier, IdentificationMethod, TrackingPoint, DataReconciliation

### 🔵 Organizational Foundation (4 entities)  
Organization, Certificate, CertificationScheme, CertificationBody

### 🟤 Material & Supply Chain (4 entities)
Material, SupplyBase, Supplier, Customer

### 🟠 Transaction Management (3 entities)
Transaction, TransactionBatch, SalesDeliveryDocument

### 🟡 Sustainability & Claims (1 entity)
Claim

### 🟣 Geographic & Location (1 entity)
GeographicData

### 🔴 Reporting & Compliance (3 entities)
SupplyBaseReport, VerificationStatement, Audit

### ⚫ Analytics & Data (2 entities)
EnergyCarbonData, MoistureContent

### 👥 Personnel (2 entities)
Operator, ProductGroup

## Access

The Interactive ERD Navigator is available at:
- **Live Site**: https://boost-working-group.github.io/BOOST/erd-navigator/
- **Main Site**: https://boost-working-group.github.io/BOOST/ (includes link to navigator)

## Technical Architecture

### Data Sources
- **Schema Files**: Loads entity definitions from `../drafts/current/schema/*/validation_schema.json`
- **Configuration**: Entity positioning and relationships defined in `erd-config.json`
- **Metadata System**: Relationships driven by `boost_metadata` sections in schemas
- **Discussion Mapping**: Direct links to GitHub discussions embedded in entity headers
- **Dynamic Rendering**: D3.js-based interactive visualization with real-time updates

### Key Technologies
- **D3.js v7**: Interactive SVG manipulation and zooming
- **JSON Schema**: Entity validation and field definitions
- **Metadata-Driven Relationships**: Automatic relationship detection from schema metadata
- **GitHub Discussions API**: Direct integration for feedback collection
- **Responsive Design**: Works on desktop, tablet, and mobile devices

### Architecture Details
For comprehensive configuration guidance, see **[ERD_CONFIGURATION.md](ERD_CONFIGURATION.md)** which covers:
- Hub-and-spoke layout design principles
- Entity positioning and spacing requirements
- Metadata-driven relationship system
- Visual design system and color coding
- Adding new entities and maintenance procedures

## Usage Instructions

### For Stakeholders
1. **Navigate**: Use filter buttons to focus on relevant thematic areas
2. **Explore**: Zoom and pan to examine entity relationships in detail  
3. **Feedback**: Click purple 💬 icons in entity headers to access discussions
4. **Focus**: Use 🎯 button to reduce visual complexity around TraceableUnit

### For Developers
- Entity definitions are dynamically loaded from schema files
- Entity positioning configured in `erd-config.json`
- Relationships defined in schema `boost_metadata` sections
- Discussion links are embedded directly in the ERD
- The navigator automatically reflects schema updates without manual intervention
- See **[ERD_CONFIGURATION.md](ERD_CONFIGURATION.md)** for detailed development guidance

## Maintenance

The navigator automatically updates when:
- **Schema files** are modified in `../drafts/current/schema/`
- **New entities** are added to the schema structure
- **Discussion links** are updated in the codebase

No manual diagram generation is required - the ERD is dynamically rendered from live schema data.

## Migration from Static Version

This interactive navigator replaced the previous static Mermaid-based ERD system, providing:
- **Dynamic schema integration** vs static entity definitions
- **Interactive filtering and exploration** vs fixed view
- **Direct discussion access** vs separate entity link sections  
- **36 entities** vs previous 16 entities
- **Advanced decluttering** with TraceableUnit focus mode

The site maintains full backward compatibility and integrates seamlessly with the existing GitHub Pages setup.