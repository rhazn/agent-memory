# Applied AI projects

User-confirmed project evidence for job assessments, application answers, and
company background. Read alongside the current CV. These details were supplied
by Philip on 12 November 2026 and are not yet published on the website. Do not
identify the client or invent implementation details, adoption figures, or model
benchmarks.

## Laboratory reports for construction-site assessments

### Problem and product

- Architects take samples at construction sites, send them to a laboratory, and
  combine the complex laboratory results into a final consumer-facing report.
- Reading lab reports and manually transferring their data was slow and prone
  to errors.
- Through Isselthal, Philip implemented an AI-powered product with a Microsoft
  Word add-in for users and a backend server that performs most of the work.
- Architects upload laboratory reports. The system ingests and parses them, then
  generates the final data tables and report text automatically.

### Approach and technologies

- Evaluated multiple extraction approaches with the Evalite framework against
  ground truth manually extracted from existing laboratory reports.
- The selected approach extracts text from each PDF and also renders its pages
  as images. Both representations go to a model with a custom prompt.
- Philip called the model "Luna" and said it is hosted on Azure for data
  protection. The exact model identifier is unverified; confirm it before using
  a more specific name. Do not silently substitute another model.
- Extractions not found in the PDF text, or containing unusual or impossible
  field values under domain-specific checks, trigger a focused repeat extraction
  with a larger model.
- This is practical experience with multimodal document extraction, grounded
  evaluation, domain-aware validation, and selective larger-model fallback.

### Reported impact and limits

- Philip reports that the architects now save approximately 3-4 hours per week
  each on manual data copying. This describes a product in actual use, not only
  a proposed prototype.
- His illustrative valuation uses approximately EUR 300 per architect-hour and
  50 working weeks: EUR 45,000-60,000 of annual time value per architect.
- EUR 60,000 is the upper-end estimate, using four hours per week. These are
  estimates of freed professional time, not independently measured cash savings,
  revenue, or net savings after software and model costs.
- Do not invent extraction accuracy, user counts, total firm-wide savings, or
  compliance certifications. Azure hosting alone does not establish compliance.

## Coaching chatbot

- Philip worked on a chatbot intended to support people returning to work after
  burnout and built evaluation tooling for response quality and safety.
- He confirms experience with multiple AI evaluation pipelines, including this
  chatbot and the laboratory-report extraction product above.
- Production launch status, specific models, and business impact of the chatbot
  remain unconfirmed. Use the laboratory project when a concrete deployed-product
  example and quantified time savings are needed.
