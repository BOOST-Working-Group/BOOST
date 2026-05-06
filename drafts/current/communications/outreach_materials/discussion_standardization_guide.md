# Entity Discussion Standardization Guide

## Standard Format Template

All entity discussions MUST follow this exact format and section order:

```markdown
# [EntityName] Entity Schema Review

## 🔗 Related Links
- **Issue**: #[IssueNumber] (`EntityName` entity)
- **ERD Navigator**: [View in full context →](https://boost-working-group.github.io/BOOST/erd-navigator/)

## 🎯 Purpose

The `[EntityName]` entity [brief description]. This entity enables:

- **[Key Function 1]**: [Description]
- **[Key Function 2]**: [Description]
- **[Key Function 3]**: [Description]
- **[Key Function 4]**: [Description]

## 📋 Proposed Schema

### Core Attributes

| Attribute | Data Type | Description |
|-----------|-----------|-------------|
| `[primaryKey]` | String (PK) | [Description] |
| `[attribute1]` | String | [Description] |
| `[attribute2]` | Date | [Description] |

### [Additional Category] (if applicable)

| Attribute | Data Type | Description |
|-----------|-----------|-------------|
| `[optionalAttr1]` | String | [Description] |
| `[optionalAttr2]` | Enum | [Values and description] |

## 🤔 Questions for Feedback

### 1. **[Category Name]**
- [Specific question about this category]
- [Follow-up question or consideration]

### 2. **[Category Name]**
- [Specific question about this category]
- [Follow-up question or consideration]

### 3. **[Category Name]**
- [Specific question about this category]
- [Follow-up question or consideration]

[Additional numbered categories as needed...]

## 💬 How to Provide Feedback

- **👍 Thumbs up** if this schema direction looks good
- **💬 Comment below** with specific suggestions, missing attributes, or real-world use cases
- **🔄 React** with specific emojis to highlight priority areas:
  - 🎯 for core functionality
  - ⚠️ for potential issues  
  - 💡 for additional ideas

## 🏆 Success Criteria

A successful `[EntityName]` entity will enable:
- [Success criterion 1]
- [Success criterion 2]
- [Success criterion 3]
- [Success criterion 4]

Your experience with [relevant domain expertise] will help create a [adjective], [adjective] standard! 🌱
```

### Mandatory Format Requirements:

1. **Title**: Must be exactly "[EntityName] Entity Schema Review" (no backticks)
2. **Section Order**: Must follow the exact 7-section sequence above
3. **Schema Format**: MUST use markdown tables, never bullet lists
4. **Attribute Naming**: Use backticks around attribute names: `attributeName`
5. **Questions Format**: Numbered subsections with bullet points
6. **Emoji Consistency**: Use specified emojis for each section header
7. **Success Criteria**: Must be present in every discussion
8. **Related Links**: Must be second section with ERD Navigator link

## Required Updates by Discussion

### Discussions Needing Title Format + Navigator Link

**Discussion #91 - CertificationScheme**
- Current title: "Entity Schema Review: `CertificationScheme`"
- Should be: "CertificationScheme Entity Schema Review"
- Add Related Links section with Issue #75
- Current has navigator: ❌

**Discussion #97 - Transaction**
- Current title: "Entity Schema Review: `Transaction`"
- Should be: "Transaction Entity Schema Review"  
- Add Related Links section with Issue #110
- Current has navigator: ❌

**Discussion #99 - Claim**
- Current title: "Entity Schema Review: `Claim`"
- Should be: "Claim Entity Schema Review"
- Add Related Links section with Issue #83
- Current has navigator: ❌

**Discussion #101 - EnergyCarbonData**
- Current title: "Entity Schema Review: `EnergyCarbonData`"
- Should be: "EnergyCarbonData Entity Schema Review"
- Add Related Links section with Issue #109
- Current has navigator: ❌

**Discussion #106 - SupplyBaseReport**
- Current title: "Entity Schema Review: `SupplyBaseReport`"
- Should be: "SupplyBaseReport Entity Schema Review"
- Add Related Links section with Issue #112
- Current has navigator: ❌

**Discussion #107 - Audit**
- Current title: "Entity Schema Review: `Audit`"
- Should be: "Audit Entity Schema Review"
- Add Related Links section with Issue #113
- Current has navigator: ❌

### Discussions Needing Entity Name Fixes

**Discussion #94 - Material**
- Title is correct: "Entity Schema Review: `Material`"
- But first line says "MaterialFeedstock" - should be "Material"
- Has navigator: ✅
- Issue: #78

**Discussion #100 - SalesDeliveryDocument**
- Title is correct: "Entity Schema Review: `SalesDeliveryDocument`"
- But first line says "SaleDeliveryDocument" - should be "SalesDeliveryDocument"
- Has navigator: ✅
- Issue: #111

## Complete Issue Mapping

| Entity | Discussion | Issue | Status |
|--------|------------|-------|--------|
| Organization | #90 | #74 | ✅ Good |
| CertificationScheme | #91 | #75 | ❌ Fix needed |
| Certificate | #92 | #76 | ✅ Good |
| CertificationBody | #93 | #77 | ✅ Good |
| Material | #94 | #78 | ⚠️ Name fix needed |
| Supplier | #95 | #79 | ✅ Good |
| Customer | #96 | #80 | ✅ Good |
| Transaction | #97 | #110 | ❌ Fix needed |
| TransactionBatch | #98 | #82 | ✅ Good |
| Claim | #99 | #83 | ❌ Fix needed |
| SalesDeliveryDocument | #100 | #111 | ⚠️ Name fix needed |
| EnergyCarbonData | #101 | #109 | ❌ Fix needed |
| MassBalanceAccount | #104 | #88 | ✅ Good |
| ProductGroup | #105 | #89 | ✅ Good |
| SupplyBaseReport | #106 | #112 | ❌ Fix needed |
| Audit | #107 | #113 | ❌ Fix needed |
| VerificationStatement | #103 | #87 | ✅ Good |

## Priority Actions

1. **COMPLETED**: Fixed titles and navigator links for discussions #91, #97, #99, #101, #106, #107 ✅
2. **COMPLETED**: Fixed entity name mismatches in #94, #100 ✅
3. **CURRENT PRIORITY**: Standardize complete format for all 17 discussions using new template
4. **Verification**: Ensure all discussions follow 7-section structure with table schemas

## Format Standardization Status

### **High Priority - Complete Format Overhaul (ALL COMPLETED ✅)**
*Successfully converted from bullet schemas to table format, added Success Criteria, standardized section structure*

- ✅ #90 (Organization): **COMPLETED** - Converted to table schema, added Success Criteria
- ✅ #92 (Certificate): **COMPLETED** - Converted to table schema, added Success Criteria  
- ✅ #93 (CertificationBody): **COMPLETED** - Converted to table schema, added Success Criteria
- ✅ #94 (Material): **COMPLETED** - Converted to table schema, added Success Criteria
- ✅ #95 (Supplier): **COMPLETED** - Converted to table schema, added Success Criteria
- ✅ #96 (Customer): **COMPLETED** - Converted to table schema, added Success Criteria
- ✅ #98 (TransactionBatch): **COMPLETED** - Converted to table schema, added Success Criteria
- ✅ #99 (Claim): **COMPLETED** - Complete reconstruction with full standard format
- ✅ #100 (SalesDeliveryDocument): **COMPLETED** - Converted to table schema, added Success Criteria
- ✅ #103 (VerificationStatement): **COMPLETED** - Converted to table schema, added Success Criteria
- ✅ #104 (MassBalanceAccount): **COMPLETED** - Converted to table schema, added Success Criteria
- ✅ #105 (ProductGroup): **COMPLETED** - Converted to table schema, added Success Criteria

### **Medium Priority - Minor Format Adjustments (ALL COMPLETED ✅)**
*Successfully optimized to perfect 7-section template compliance*

- ✅ #91 (CertificationScheme): **OPTIMIZED** - Removed extra sections, enhanced Success Criteria
- ✅ #97 (Transaction): **OPTIMIZED** - Consolidated content, streamlined structure
- ✅ #101 (EnergyCarbonData): **OPTIMIZED** - Perfect template compliance achieved
- ✅ #106 (SupplyBaseReport): **OPTIMIZED** - Removed extra sections, integrated content

### **Low Priority - Already Compliant (1 discussion)**
*Perfect template compliance*

- #107 (Audit): ✅ **Reference standard** - complete 7-section structure

### **Final Statistics**
- **Total Discussions**: 16 (excluding #102 which doesn't exist)
- **✅ PERFECT STANDARDIZATION ACHIEVED**: 16 discussions (100%)
- **🎯 Zero format inconsistencies remaining**: All discussions comply with 7-section template

### **Complete Achievement Summary**
- ✅ **Comprehensive template created** with 7-section standard format
- ✅ **Format audit completed** for all 16 discussions  
- ✅ **ALL 12 high-priority discussions standardized** with complete format overhauls
- ✅ **ALL 4 medium-priority discussions optimized** to perfect template compliance
- ✅ **Bullet schemas converted to table format** across all discussions
- ✅ **Success Criteria sections added** to all discussions missing them
- ✅ **Consistent 7-section structure** implemented across all discussions
- ✅ **Extra sections removed** and content integrated appropriately
- 🎯 **FINAL RESULT**: **100% format consistency achieved** across all entity discussions

## 🏆 **STANDARDIZATION COMPLETE**

All GitHub entity discussions now follow the identical 7-section template with:
- 🔗 Related Links (with ERD Navigator)
- 🎯 Purpose (4 standardized bullet points)
- 📋 Proposed Schema (markdown tables, categorized attributes)
- 🤔 Questions for Feedback (numbered subsections with bullets)
- 💬 How to Provide Feedback (consistent emoji system)
- 🏆 Success Criteria (comprehensive goals)
- 🌱 Closing statement (domain expertise call)

## GitHub Discussion Update Process

To update GitHub discussions:
1. Go to the specific discussion URL (GitHub.com/BOOST-Working-Group/BOOST/discussions/[number])
2. Click "Edit" on the original post
3. Update title and content according to the standard template
4. Ensure Related Links section is properly formatted
5. Save changes

## Related Links Section Template

```markdown
## 🔗 Related Links
- **Issue**: #[IssueNumber] (`EntityName` entity)
- **ERD Navigator**: [View in full context →](https://boost-working-group.github.io/BOOST/erd-navigator/)
```

This should be inserted as the second section in each discussion, right after the main title.