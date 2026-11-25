# RoastVeld — proposed AWS architecture

RoastVeld runs on AWS so imports, model training and dashboards scale with your production — and every roastery’s data stays separate.

## Request flow

1. Roast logs
2. Amazon S3
3. AWS Lambda
4. DynamoDB
5. SageMaker AI
6. Head roaster
7. Bedrock summary

## Services

### Amazon SageMaker AI

**Role:** Forecast consistency

Trains models that link roast variables and green-coffee attributes to cupping outcomes, then forecasts each product’s consistency and flags drifting batches.

### Amazon S3

**Role:** Hold roast logs and cupping files

Stores raw exports from roaster software and cupping spreadsheets, encrypted and versioned so analyses can always be traced to their source files.

### Amazon DynamoDB

**Role:** Keep the production history

Stores every linked batch — curve metrics, lot, product, cup score and review notes — with fast reads for dashboards and trial comparisons.

### AWS Lambda

**Role:** Normalise and join data

Parses different roaster export formats, links batches to lots and cupping records, and triggers re-scoring when new results arrive.

### Amazon Bedrock

**Role:** Explain changes in plain language

Drafts weekly production summaries and trial comparisons from confirmed data, so the head roaster can share findings quickly — after editing them.

## Principles

- **Cuppers stay in charge** — Models learn from your Q graders — they don’t replace them.
- **Honest uncertainty** — Forecasts always show their confidence range.
- **Your recipes stay yours** — Profiles and results are private to your roastery.

## Safeguards

- **Cupping stays human** — Sensory evaluation is done by your team. RoastVeld analyses the results, it doesn’t taste the coffee.
- **Explained forecasts** — Every flag shows which variables drove it and which batches it’s based on.
- **Commercial quality only** — We analyse consistency, not food safety. Safety testing remains with your accredited processes.
- **Profiles protected** — Roast profiles are commercially sensitive — encrypted and visible only to your team.

## MVP scope

We import six to twelve months of your roast logs and cupping records, link them, and deliver product-level consistency reports and forecasts your head roaster reviews every week.

- Roast log and cupping imports
- Batch-to-cup linking
- Product consistency dashboards
- Six-week consistency forecasts
- Weekly quality performance report
