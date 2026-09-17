# claude_did_it
sovereign-validation-loop is a deterministic, air-gapped CLI test harness for local LLM dual-model orchestration. It runs an adversarial Generator-Validator loop with strict regex telemetry logging and forces surgical inter-case VRAM purging via keep_alive=>0 to isolate memory footprints and prevent multi-tenant RAM port collisions.
