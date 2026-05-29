# Top Chart - Open Sports Data Standard

[![License: CC0](https://img.shields.io/badge/License-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

## What This Is

An **open standard** for sports data that lets federations publish results in a unified format while keeping 100% control of their systems.

**Not a proprietary platform.** Just a standard everyone can use freely.

## The Problem

Sports data is fragmented across Europe:

- CYSAF publishes PDFs (sailing)
- CMF publishes Excel (motorsports)
- Small clubs: HTML or nothing
- No federation wants to replace their system
- Data silos prevent aggregation

## The Solution

**Open Standard Model:**

```
Federation keeps their system
        ↓
Publishes results to standard (REST API, JSON, CSV)
        ↓
TopChart aggregates (optional premium layer)
        ↓
Athletes see unified data across competitions
```

## Core Concept

### Event-Centric Data Model

Simple, universal format:

```json
EVENT METADATA:
{
  "event_id": "uuid",
  "event_name": "CYSAF Championship 2025",
  "event_date": "2025-06-14",
  "location": "Larnaca",
  "sport": "sailing",
  "federation": "CYSAF"
}

FLAT RESULTS TABLE (one row = one athlete):
[
  {
    "event_id": "...",
    "athlete_name": "Petros G.",
    "club": "Marina",
    "class": "ORC-A",
    "position": 1,
    "points": 9
  }
]
```

## How to Use

### For Federations

1. Define your data in the standard format
1. Publish via REST API, JSON files, or CSV
1. Optionally: Subscribe to TopChart premium features

No switching costs. No vendor lock-in.

### For Developers

```python
# Python example
from topchart import publish_results

federation = TopChartPublisher(federation_id="cysaf")
federation.publish_event(event_data)
```

```javascript
// JavaScript example
import { TopChartPublisher } from '@topchart/sdk';

const federation = new TopChartPublisher('cysaf');
await federation.publishEvent(eventData);
```

```go
// Go example
import "github.com/topchart/publish"

federation := publish.NewPublisher("cysaf")
federation.PublishEvent(eventData)
```

## Key Features

✅ **Open Standard (CC0)** - Use freely, no lock-in
✅ **Federation-Friendly** - Keep your system, just publish to standard
✅ **Interoperable** - Plug into any aggregator (TopChart or others)
✅ **Simple** - Event-centric, flat results, no complexity
✅ **Network Effects** - More federations = more valuable data

## Architecture

### Layer 1: Open Standard (This Repository)

- JSON Schema specification
- REST API specification
- Data model definition
- Publishing guidelines

### Layer 2: Reference Implementations

- Python library
- JavaScript SDK
- Go package

### Layer 3: Optional Aggregator (TopChart)

- Beautiful UI for results
- Cross-federation analytics
- Sponsorship integration
- Premium features

**Important:** Standard works WITHOUT Layer 3. TopChart is optional.

## Real-World Analogy

- **RSS** = open standard (everyone publishes)
- **Google Reader** = aggregator (showed RSS beautifully)
- **TopChart** = optional aggregator for sports data

RSS worked without Google Reader. So does this standard.

## Licensing

```
Standard specification: CC0 (Public Domain)
Reference implementations: MIT (fork freely)
```

## For Federations Adopting the Standard

### Getting Started

1. **Read the specification** (in `/spec/`)
1. **Choose implementation** (Python, JS, or Go)
1. **Publish your first event**
1. **Optional: Use TopChart** for premium features

### Benefits

✅ Official results (ground truth data from spotters if needed)
✅ Beautiful display (optional TopChart premium)
✅ Cross-federation visibility
✅ Athlete tracking across events
✅ Analytics and insights

## Examples

See `/examples/` for:

- Sample event data
- API request/response
- Federation setup guide
- Integration patterns

## Contributing

This is an open standard. Improvements welcome!

Submit issues or pull requests for:

- Schema improvements
- New fields
- Use cases
- Implementation bugs

## Contact

**Project Lead:** Aleksandr Fediaev
**LinkedIn:** linkedin.com/in/artiman

-----

**Open sports data infrastructure for everyone.** 🚀

Made with ❤️ for European sports federations.
