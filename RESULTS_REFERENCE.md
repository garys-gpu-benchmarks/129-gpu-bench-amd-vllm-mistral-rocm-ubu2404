# Results: 129 vLLM Token-Generation Benchmark

**Main goal:** Measure vLLM token generation rate  
**Tools:** Start python -m vllm.entrypoints.openai.api_server on port 8000, then run scripts/benchmark_serving.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_149 · recorded 2026-11-19). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× AMD Instinct MI300X VF (196288 MB) · INTEL(R) XEON(R) PLATINUM 8568Y+ · Ubuntu 24.04.5 LTS · kernel 6.8.0-149-generic · driver 7.1.9.31600000
- **Run:** 2026-11-19T22:29:20Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 03:31 · benchmark 00:07 · whole run 05:03
- **Source:** run 129_20261119_222920
- **Command:** `bash run_benchmark.sh --smoke --model-name mistralai/Mistral-7B-v0.3 --dtype bfloat16 --tensor-parallel-size 1 --gpu-memory-utilization 0.9 --input-len 64 --output-len 16 --max-num-seqs 2 --max-concurrency 2`

| # | Metric | Result |
|---|---|---|
| 1 | Generated token rate (output_token_throughput_tokens_sec) | 374.1887106388066 |
| 2 | TPOT, ms (time_per_output_token_tpot_p50_msec) | 4.462982266644151 |
| 3 | Time To First Token, ms (ttft_p50_msec) | 13.470877000145265 |
| 4 | ITL, ms (inter_token_latency_itl_p50_msec) | 4.6800569998595165 |
| 5 | End-to-end request latency p50, ms (end_to_end_request_latency_msec) | 80.41561099980754 |
<!-- /profile:smoke -->
