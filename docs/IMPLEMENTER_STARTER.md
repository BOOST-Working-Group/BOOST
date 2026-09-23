# BOOST for implementers: a starter page

For software teams asked "what would it take to build on this standard." Everything linked here is public and openly licensed.

## What BOOST is

An open data model for wood and biomass moving through a supply chain: what was harvested where, what it was turned into, who handled it, and the claims that travel with it. It is published by the W3C BOOST Community Group under the W3C Software and Document License. It is a data standard, not a platform: any tool that emits and reads its entities is interoperable with any other.

## Read first

- Specification (HTML): https://Biogenics-Traceability.github.io/BOOST/boost-spec.html
- Specification (PDF): https://Biogenics-Traceability.github.io/BOOST/boost-spec.pdf
- Interactive entity map (36 entities, 7 thematic areas): https://Biogenics-Traceability.github.io/BOOST/erd-navigator/
- Repository: https://github.com/Biogenics-Traceability/BOOST
- JSON Schemas, one directory per entity, with examples: `drafts/current/schema/`
- Worked examples: `drafts/current/examples/`
- JSON-LD context: `drafts/current/specifications/biomass_coc_context.jsonld`
- Validator (open source; checks a payload against the schemas): https://github.com/Biogenics-Traceability/boost-validator
- Community Group and charter: https://www.w3.org/community/boost-01/

## The minimum an implementation emits

A first-mile tool does not need all 36 entities. The core traceability set is:

- `Organization` and `Operator`: who.
- `TrackingPoint` and `GeographicData`: where, with plot or harvest-site geometry (GeoJSON).
- `TraceableUnit`: the thing being tracked, with `SpeciesComponent` for composition and `MeasurementRecord` for volume or mass.
- `MaterialProcessing`: a transformation (harvest, chipping, sawing, drying) with inputs and outputs.
- `Transaction` and `SalesDeliveryDocument`: the change of custody.
- `Claim`, `Certificate`, `CertificationScheme`: the claims that travel with the unit.

Emit those correctly and the validator passes; the rest of the model is there when a use case needs it.

## How it relates to the Global Traceability Framework

The Global Traceability Framework is the commodity-agnostic core published by IFT with the GDST partners (https://traceabilityforall.helpdocs.io/category/6j3u1vj9c5-the-global-traceability-framework): seven critical tracking events and eight key data elements, expressed as a profile of GS1 EPCIS 2.0. A 2026 alignment analysis found the BOOST model conforms to it without redesign; four additions are open in the issue tracker, chiefly EPCIS vocabulary emission on event-bearing entities (#298), harvest-claim evidence (#295), and separating regulatory-filing fields from the commercial transaction record (#296). The timber Module of the Framework, in public working draft from mid-November 2026, is a profile of this model: it names the mandatory and optional data elements for timber against the Framework's events.

## Direction of travel

The UN Transparency Protocol's 1.0 release carries traceability events as EPCIS wrapped in W3C Verifiable Credentials, so that a record can be verified without a network connection between the parties. BOOST payloads are JSON-LD already; the work ahead is the credential envelope, resolvable identifiers for parties and facilities, and registration of the timber Module as a UNTP extension. Implementers who emit EPCIS-shaped events now will not have to redo them.

## Getting help

Open an issue in the repository, or join the Community Group. The chair (Peter Tittmann, peter@arbos.bio) will do a walkthrough call with any team assessing an implementation.
