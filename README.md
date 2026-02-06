diff --git a/README.md b/README.md
index 94d784c772c467a9c7a197daedb98b84e76e71e0..5445e387f271ecc204dfa13fe478b04a7016a068 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,31 @@
-# bioinfoirmatics
\ No newline at end of file
+# bioinfoirmatics
+
+A lightweight biotechnology assistant that runs on a local web page with a JavaScript (Express) server, a Python analysis engine, and an R statistics helper.
+
+## Features
+- Answers biotech questions with a postdoctoral-level framing.
+- Executes common sequence tasks (GC content, reverse complement, translation, primer Tm, FASTA summaries) directly.
+- Provides quick descriptive statistics through R.
+- Avoids external links unless the user explicitly asks for them.
+
+## Run locally
+This server uses only built-in Node.js modules, so you do not need `npm install`.
+
+```bash
+node server.js
+```
+
+Then open `http://localhost:3000`.
+
+## Example prompts
+- "Calculate GC content for ATGGCCATTGTAATGGGCCGCTGAAAGGGTGCCCGATAG"
+- "Translate this sequence and estimate primer Tm: ATGGCCATTGTAATGGGCCGCTGAAAGGGTGCCCGATAG"
+- "What tools should I use for single-cell RNA-seq QC and clustering?"
+
+## R stats helper
+Enter comma-separated values (e.g., `10, 12.5, 11.8, 9`) in the UI or call:
+```bash
+curl -X POST http://localhost:3000/api/r-stats \
+  -H "Content-Type: application/json" \
+  -d '{"values":[10,12.5,11.8,9]}'
+```
