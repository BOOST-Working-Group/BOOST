# BOOST Schema Directory

This directory contains JSON schema definitions for all BOOST entities. These schema files serve as the single source of truth for entity structure and are automatically consumed by the BOOST ERD visualization.

## Quick Reference: Entity/Attribute/Relationship Management

### Adding New Entities
1. **Create directory**: `mkdir drafts/current/schema/new_entity_name`
2. **Create schema**: Add `validation_schema.json` with `{"schema": {...}}` wrapper
3. **Add boost_metadata**: Include `area`, `emoji`, `position`, and `relationships`
4. **Refresh ERD**: Entity appears automatically with relationships

### Adding Attributes to Existing Entities
1. **Edit schema**: Modify `properties` section in `validation_schema.json`
2. **Update required**: Add to `required` array if mandatory
3. **Refresh ERD**: Fields appear automatically with proper types

### Adding Relationships
1. **Edit boost_metadata**: Add to `relationships` array in schema file
2. **Use correct entity names**: Ensure PascalCase names match exactly
3. **Verify both entities exist**: Source and target must both be loaded
4. **Refresh ERD**: Relationships draw automatically

### Key Requirements
- ✅ All schemas need `{"schema": {...}}` wrapper
- ✅ Entity names must be PascalCase (e.g., "LcfsPathway", not "LCFSPathway")
- ✅ Directory names use snake_case (e.g., "lcfs_pathway")
- ✅ boost_metadata is required for ERD integration
- ✅ Update `directories.json` manifest when adding new entities
- ✅ Foreign key fields must use `EntityNameId` convention

### Schema Directory Manifest
The `directories.json` file contains a comprehensive list of all schema directories for reliable ERD Navigator discovery across all platforms (GitHub Pages, local development, etc.). 

**When adding new entities:**
1. Create your schema directory and files as usual
2. Add the directory name to `directories.json` in the `schema_directories` array
3. Update the `total_entities` count and `last_updated` timestamp

This ensures the ERD Navigator can discover all entities regardless of deployment environment.

### EntityNameId Foreign Key Convention

BOOST uses a standardized `EntityNameId` convention for foreign key fields that enables automatic relationship detection in the ERD Navigator with zero configuration.

**Convention Rule:** Foreign key fields must be named exactly `EntityNameId` where `EntityName` matches the target entity's PascalCase name.

**Examples:**
```json
{
  "properties": {
    "OrganizationId": {
      "type": "string", 
      "description": "References Organization entity"
    },
    "TraceableUnitId": {
      "type": "string",
      "description": "References TraceableUnit entity" 
    },
    "CertificationBodyId": {
      "type": "string",
      "description": "References CertificationBody entity"
    }
  }
}
```

**Benefits:**
  - ✅ **Automatic relationship detection** - ERD Navigator creates relationships without manual boost_metadata
  - ✅ **Semantic relationship labels** - Converts to meaningful names like `references_organization`
  - ✅ **Identifying vs non-identifying** - Uses `required` array to determine relationship type
  - ✅ **Zero maintenance** - No hardcoded mappings or complex matching logic
  - ✅ **Linked data ready** - Follows semantic web conventions for future JSON-LD integration

**Relationship Types:**
  - Fields in `required` array → **identifying relationships** (solid lines)
  - Optional fields → **non-identifying relationships** (dashed lines)

**Migration from Legacy FK Names:**
  - `organizationId` → `OrganizationId`
  - `traceableUnitId` → `TraceableUnitId`  
  - `cbId` → `CertificationBodyId`
  - `geographicDataId` → `GeographicDataId`

## Overview

Each entity in the BOOST data model has its own subdirectory containing:
- `validation_schema.json` - JSON schema definition with field types, constraints, and validation rules
- `*_example.json` - Example data instances 
- `*_dictionary.md` - Human-readable field descriptions

## Directory Structure

```
schema/
├── traceable_unit/           # Core entity for biomass tracking
│   ├── validation_schema.json
│   ├── traceable_unit_example.json
│   └── traceable_unit_dictionary.md
├── material/                 # Material types and specifications  
│   ├── validation_schema.json
│   ├── material_example.json
│   └── material_dictionary.md
├── organization/             # Business entities (enhanced with LCFS fields)
├── transaction/              # Business transactions (enhanced with LCFS fields)
├── lcfs_pathway/             # CARB-certified fuel pathways for LCFS compliance  
├── lcfs_reporting/           # Quarterly LCFS compliance reports
├── energy_carbon_data/       # Energy and carbon data (enhanced with LCFS fields)
├── [22+ other entities]/
└── README.md                 # This file
```

## LCFS Integration

The BOOST schema now includes comprehensive support for California's Low Carbon Fuel Standard (LCFS) program compliance. This integration enables organizations to track fuel transactions, calculate credits/deficits, and generate quarterly compliance reports.

### LCFS-Specific Entities

#### LCFSPathway
- **Purpose**: Represents CARB-certified fuel pathways with carbon intensity data
- **Key Fields**: `pathwayId`, `carbonIntensity`, `energyEconomyRatio`, `feedstockCategory`
- **Usage**: Links transactions to certified pathways for credit calculation

#### LCFSReporting  
- **Purpose**: Quarterly compliance reports submitted to CARB
- **Key Fields**: `reportingPeriod`, `totalCreditsGenerated`, `netPosition`, `complianceStatus`
- **Usage**: Aggregates transaction data for regulatory submission

### Enhanced Core Entities

#### Organization (LCFS Enhancements)
- **New Fields**: `lcfsRegistrationId`, `regulatedEntityType`, `facilityCapacity`, `operationalStatus`  
- **Purpose**: Track LCFS registration status and regulated entity classification

#### Transaction (LCFS Enhancements)
- **New Fields**: `lcfsPathwayId`, `fuelVolume`, `fuelCategory`, `reportingPeriod`, `regulatedPartyRole`
- **Purpose**: Link fuel transactions to LCFS pathways for credit calculation

#### EnergyCarbonData (LCFS Enhancements)
- **New Fields**: `lcfsPathwayType`, `energyEconomyRatio`, `lifeCycleStage`, `regulatoryBenchmark`
- **Purpose**: Support LCFS carbon intensity calculations and lifecycle assessments

### LCFS Workflow Integration

1. **Pathway Certification**: LCFSPathway entities store CARB-certified pathways
2. **Transaction Tracking**: Enhanced Transaction entities link fuel sales to pathways
3. **Credit Calculation**: System calculates credits using `(Benchmark_CI - Pathway_CI) × Fuel_Volume_MJ × EER`
4. **Quarterly Reporting**: LCFSReporting entities aggregate transactions for CARB submission
5. **Compliance Monitoring**: Track credit/deficit positions and submission deadlines

## Schema Integration with ERD

The BOOST ERD Navigator (`../../erd-navigator/index.html`) **dynamically loads these schema files** instead of using hardcoded definitions. This means:

✅ **Schema changes automatically appear in the ERD**  
✅ **Field additions/removals are immediately reflected**  
✅ **Type changes update ERD display**  
✅ **Relationships from schema metadata are automatically processed**
✅ **Single source of truth maintained**

### ERD Configuration and Positioning

For comprehensive guidance on ERD configuration, including entity positioning, relationship examples, and visual design principles, see the **[ERD Configuration Guide](../../erd-navigator/ERD_CONFIGURATION.md)**.

The guide covers:
- **Hub-and-spoke layout design** with TraceableUnit as the central hub
- **Entity positioning system** and coordinate management  
- **Relationship configuration** using `boost_metadata` sections
- **Visual design system** with thematic color coding
- **Adding new entities** and maintenance procedures
- **Troubleshooting** common configuration issues

### Boost Metadata for ERD Integration

Each schema file should include a `boost_metadata` section for ERD integration:

```json
{
  "boost_metadata": {
    "entity": {
      "name": "EntityName",
      "primaryKey": "entityId",
      "area": "core_traceability", 
      "description": "Entity description with emoji"
    },
    "relationships": [
      {
        "field": "targetEntityId",
        "targetEntity": "TargetEntity",
        "relationshipType": "many-to-one",
        "required": true,
        "label": "relationship description",
        "example": "Concrete example showing the relationship"
      }
    ]
  }
}
```

This metadata enables automatic ERD positioning, relationship detection, and interactive examples.

### Automatic Entity and Relationship Discovery

The ERD Navigator now includes a powerful auto-discovery system that:

1. **Scans schema directories**: Automatically finds all entity schema files
2. **Extracts relationships**: Processes `boost_metadata.relationships` from schema files  
3. **Merges with static relationships**: Combines schema-defined and hardcoded relationships
4. **Positions entities**: Auto-calculates positions by functional area if not specified

This means **new entities automatically appear in the ERD** without any manual ERD Navigator code changes!

### For Schema Maintainers

When you modify a `validation_schema.json` file:
1. **Add/remove fields**: They automatically appear/disappear in the ERD
2. **Change field types**: ERD display updates to reflect new types  
3. **Modify required fields**: ERD styling updates accordingly
4. **Update descriptions**: Available for future tooltip integration

## Quick Start

### Editing Existing Entities

To see your schema changes in the ERD:

1. **Edit any `validation_schema.json` file** in this directory
2. **Refresh the ERD Navigator** (`../../erd-navigator/index.html`)
3. **Changes appear automatically** - no manual updates needed

### Example: Adding a Field

```json
{
  "schema": {
    "properties": {
      "existingField": {"type": "string"},
      "newField": {                    # ← Add this
        "type": "string",
        "description": "My new field"
      }
    },
    "required": ["existingField", "newField"]  # ← Add to required if needed
  }
}
```

The ERD will automatically show `newField` in the entity with appropriate styling.

## Adding New Entities with Auto-Discovery

The ERD Navigator now supports **automatic entity discovery**. Follow these steps to add a new entity that will automatically appear in the ERD with its relationships:

### Step 1: Create Schema Directory

Create a new directory using `snake_case` naming:

```bash
mkdir drafts/current/schema/new_entity_name
```

### Step 2: Create validation_schema.json with boost_metadata

Create the schema file with the **required wrapper format** and include `boost_metadata` for ERD integration:

```json
{
  "schema": {
    "$schema": "http://json-schema.org/draft-07/schema#",
    "$id": "https://github.com/BOOST-Working-Group/BOOST/schemas/new-entity-name",
    "title": "New Entity Name",
    "description": "Description of the new entity",
    "boost_metadata": {
      "area": "core_traceability",
      "emoji": "⚙️", 
      "position": { "x": 2000, "y": 1000 },
      "relationships": [
        {
          "from": "NewEntityName",
          "to": "Organization",
          "label": "managed_by",
          "type": "non-identifying",
          "from_cardinality": "many",
          "to_cardinality": "one"
        }
      ]
    },
    "type": "object",
    "properties": {
      "@context": { "type": "object" },
      "@type": { "type": "string", "const": "NewEntityName" },
      "@id": { "type": "string", "format": "uri" },
      "entityId": { 
        "type": "string", 
        "description": "Unique identifier" 
      },
      "entityName": {
        "type": "string",
        "description": "Human-readable name"
      }
    },
    "required": ["@context", "@type", "@id", "entityId", "entityName"],
    "additionalProperties": false
  }
}
```

### Step 3: Configure boost_metadata

#### Required Schema Wrapper
**Critical**: All schema files must have the `{"schema": {...}}` wrapper for the ERD Navigator to load them correctly.

#### Functional Areas (area)
Choose from existing areas for consistent coloring and grouping:
- `core_traceability` - 🟢 Green (central tracking entities)
- `organizational_foundation` - 🔵 Blue (business entities)  
- `material_supply_chain` - 🟤 Brown (material and supply entities)
- `transaction_management` - 🟠 Orange (transaction entities)
- `sustainability_claims` - 🟡 Yellow (sustainability entities)
- `geographic_location` - 🟣 Purple (location entities)
- `reporting_compliance` - 🔴 Red (reporting entities)
- `analytics_data` - ⚫ Black (analytics entities)

#### Position Coordinates (position)
- Set `x` and `y` coordinates to position the entity in the ERD
- Use `null` for auto-positioning within the functional area
- Coordinate system: (0,0) is top-left, extends to (3200, 2000)
- Common positions by area:
  - Core traceability: x: 500-1500, y: 400-1200
  - Organizational: x: 500-1500, y: 1400-2000  
  - Material supply: x: 1700-2400, y: 400-1200
  - Transaction: x: 1700-2400, y: 1400-2000
  - Reporting: x: 2600-3200, y: 400-1200

#### Relationships (relationships)
Define relationships in the `relationships` array using this format:

```json
{
  "from": "SourceEntityName",      // PascalCase entity name
  "to": "TargetEntityName",        // PascalCase entity name  
  "label": "relationship_label",   // snake_case description
  "type": "non-identifying",       // "identifying" or "non-identifying"
  "from_cardinality": "many",      // "one" or "many"
  "to_cardinality": "one"          // "one" or "many"
}
```

**Important**: Both source and target entities must exist in the ERD for the relationship line to appear.

### Step 4: Naming Conventions

#### Directory to Entity Name Conversion
The auto-discovery system converts directory names to entity names:
- Directory: `my_new_entity` → Entity: `MyNewEntity`
- Directory: `lcfs_pathway` → Entity: `LcfsPathway`
- Directory: `supply_base_report` → Entity: `SupplyBaseReport`

**Rule**: `snake_case` directory names are converted to `PascalCase` entity names.

#### Field Naming for Key Detection

**Primary Keys**: Detected when field name contains "id" + entity name:
- `newEntityId` in `NewEntity` ✅
- `organizationId` in `Organization` ✅
- `id` in any entity ✅

**Foreign Keys**: Detected when field name ends with "Id" but is not a primary key:
- `organizationId` in other entities ✅
- `materialTypeId` ✅
- `geographicDataId` ✅

### Step 5: Verification

After creating the schema file:

1. **Refresh the ERD Navigator** 
2. **Check browser console** for any loading errors
3. **Verify entity appears** in the correct functional area
4. **Confirm relationships** are drawn to target entities

The entity will automatically:
- ✅ Appear in the ERD visualization
- ✅ Show all defined relationships  
- ✅ Be positioned appropriately
- ✅ Work with filtering and focus features
- ✅ Display proper field types and keys

### Common Issues and Solutions

#### Entity Not Appearing
- ❌ Missing `"schema"` wrapper → ✅ Add `{"schema": {...}}` wrapper
- ❌ Invalid JSON syntax → ✅ Validate JSON format
- ❌ Wrong directory naming → ✅ Use `snake_case` for directory names

#### Relationships Not Showing  
- ❌ Target entity doesn't exist → ✅ Ensure both entities have valid schemas
- ❌ Entity names don't match → ✅ Check PascalCase entity names exactly
- ❌ Missing relationship target → ✅ Verify target entity is loaded in ERD

#### Positioning Issues
- ❌ Entity appears in wrong area → ✅ Check `boost_metadata.area` value
- ❌ Entity overlaps others → ✅ Adjust `position` coordinates or use `null` for auto-positioning

## Architecture

### Components

1. **Schema Loading (`loadSchemaFile`)**
   - Fetches JSON schema files from the file system
   - Handles missing files gracefully
   - Uses proper path conversion for entity names

2. **Schema Conversion (`convertSchemaToEntity`)**
   - Converts JSON schema properties to ERD field format
   - Automatically detects primary and foreign keys
   - Maps schema types to display types

3. **Entity Metadata (`entityMetadata`)**
   - Maintains visual positioning and styling information
   - Preserves entity area assignments and descriptions

4. **Async Initialization (`loadEntitiesFromSchema`)**
   - Orchestrates the loading and conversion process
   - Provides fallback to static definitions

## File Structure

```
/drafts/current/
├── images/current/
├── erd-navigator/
│   └── index.html                      # Main ERD Navigator with dynamic loading
│   └── DYNAMIC_SCHEMA_LOADING.md       # This documentation
└── schema/
    ├── traceable_unit/
    │   └── validation_schema.json       # TraceableUnit schema
    ├── material/
    │   └── validation_schema.json       # Material schema
    └── [other entities]/
        └── validation_schema.json
```

## Schema File Path Convention

Entity names are converted to file paths using the following pattern:
- `TraceableUnit` → `traceable_unit/validation_schema.json`
- `MaterialProcessing` → `material_processing/validation_schema.json`
- `EnergyCarbonData` → `energy_carbon_data/validation_schema.json`

**Conversion Rule**: CamelCase → snake_case with underscores

## Schema to ERD Mapping

### Field Type Mapping

| Schema Type | ERD Display Type | Notes |
|-------------|------------------|-------|
| `string` | `string` | Default string type |
| `number` | `decimal` | Numeric values |
| `integer` | `integer` | Whole numbers |
| `boolean` | `boolean` | True/false values |
| `array` | `array` | List of items |
| `object` | `object` | Complex nested data |
| `string` with `enum` | `enum` | Enumerated values |
| `string` with `format: "date-time"` | `datetime` | Timestamps |

### Key Detection Rules

#### Primary Keys (PK)
A field is considered a Primary Key if:
- Field name contains "id" (case-insensitive)
- AND field name contains the entity name (case-insensitive)
- OR field name is exactly "id"

**Examples**: 
- `traceableUnitId` in TraceableUnit entity ✅
- `materialId` in Material entity ✅
- `id` in any entity ✅

#### Foreign Keys (FK)
A field is considered a Foreign Key if:
- Field name ends with "Id"
- AND it's not a Primary Key

**Examples**:
- `organizationId` ✅
- `materialTypeId` ✅
- `currentGeographicDataId` ✅

### Required Fields
Fields are marked as required based on the `required` array in the JSON schema.

### Ignored Fields
The following JSON-LD context fields are automatically excluded:
- `@context`
- `@type` 
- `@id`

## Entity Metadata Configuration

Each entity requires metadata for visual display:

```javascript
const entityMetadata = {
    'EntityName': {
        area: 'functional_area',           // Color/grouping area
        description: 'Entity description', // Tooltip description
        position: { x: 100, y: 200 }      // ERD coordinates
    }
};
```

### Functional Areas

| Area | Color | Description |
|------|-------|-------------|
| `core_traceability` | 🟢 Green | Central tracking entities |
| `organizational_foundation` | 🔵 Blue | Business entities |
| `material_supply_chain` | 🟤 Brown | Material and supply entities |
| `transaction_management` | 🟠 Orange | Transaction entities |
| `sustainability_claims` | 🟡 Yellow | Sustainability entities |
| `geographic_location` | 🟣 Purple | Location entities |
| `reporting_compliance` | 🔴 Red | Reporting entities |
| `analytics_data` | ⚫ Black | Analytics entities |
| `personnel` | 👥 Gray | Personnel entities |

## Usage

### Loading Process

1. **Initialization**: When the ERD loads, it calls `initializeVisualization()`
2. **Schema Loading**: `loadEntitiesFromSchema()` fetches all schema files
3. **Conversion**: Each schema is converted to ERD entity format
4. **Rendering**: Entities are drawn with their schema-defined fields
5. **Fallback**: If loading fails, static entities are used as backup

### Console Output

The loading process provides detailed console logging:

```
Loaded 25 entities from schema files
```

Or in case of issues:
```
Could not load schema for EntityName: 404
No entities loaded from schemas, falling back to static entities
```

## Error Handling

### Missing Schema Files
- Individual missing files are logged as warnings
- ERD continues loading other entities
- Falls back to static definition if available

### Network Issues
- Fetch errors are caught and logged
- ERD falls back to static entities completely
- User sees visual feedback in console

### Invalid Schema Format
- Malformed JSON is handled gracefully
- Entity is skipped with warning message
- ERD continues with remaining entities

## Benefits

### For Developers
- ✅ Single source of truth for entity definitions
- ✅ Automatic synchronization between schema and ERD
- ✅ No manual maintenance of duplicate entity lists
- ✅ Type safety and consistency validation

### For Schema Maintenance
- ✅ Changes to JSON schemas immediately reflect in ERD
- ✅ Field additions/removals are automatically detected
- ✅ Type changes are reflected in visual display
- ✅ Required field changes update styling

## Future Enhancements

This foundation enables several future features:

### Live Editing
- Real-time schema editing interface
- Immediate ERD updates on schema changes
- Schema validation and error reporting

### Advanced Features
- Schema diff visualization
- Version control integration
- Collaborative editing capabilities
- Export functionality to various formats

## Troubleshooting

### ERD Shows Static Entities Instead of Schema
**Problem**: ERD falls back to hardcoded entities
**Solutions**:
1. Check browser console for error messages
2. Verify schema file paths are correct
3. Ensure schema files have valid JSON format
4. Check file permissions and accessibility

### Missing Entities in ERD
**Problem**: Some entities don't appear in the visualization
**Solutions**:
1. Verify entity name exists in `entityMetadata`
2. Check schema file exists at expected path
3. Ensure schema has valid `properties` section
4. Look for console warning messages

### Incorrect Field Types or Keys
**Problem**: Fields show wrong types or PK/FK detection is incorrect
**Solutions**:
1. Review field naming conventions for key detection
2. Check schema type definitions match expected mappings
3. Verify `required` array includes intended fields
4. Update type mapping logic if needed

### Performance Issues
**Problem**: ERD loads slowly
**Solutions**:
1. Check network performance for schema file loading
2. Consider adding loading indicators
3. Implement schema caching for repeated loads
4. Optimize schema file sizes

## Technical Implementation Details

### Schema Loading Function
```javascript
async function loadSchemaFile(entityName) {
    const schemaPath = `../../schema/${entityName.toLowerCase().replace(/([A-Z])/g, '_$1').substring(1)}/validation_schema.json`;
    const response = await fetch(schemaPath);
    return await response.json();
}
```

### Type Detection Logic
```javascript
// Primary Key Detection
if (fieldName.toLowerCase().includes('id') && 
    (fieldName.toLowerCase().includes(entityName.toLowerCase()) || fieldName === 'id')) {
    isPK = true;
}

// Foreign Key Detection  
if (fieldName.endsWith('Id') && !isPK && fieldName !== 'id') {
    isFK = true;
}
```

### Entity Structure Output
```javascript
{
    id: 'EntityName',
    name: 'EntityName', 
    area: 'functional_area',
    description: 'Entity description',
    fields: [
        {
            name: 'fieldName',
            type: 'fieldType',
            isPK: boolean,
            isFK: boolean,
            required: boolean
        }
    ],
    x: number,
    y: number
}
```

---

*This documentation reflects the implementation as of the dynamic schema loading integration. For questions or issues, check the browser console output and verify schema file accessibility.*