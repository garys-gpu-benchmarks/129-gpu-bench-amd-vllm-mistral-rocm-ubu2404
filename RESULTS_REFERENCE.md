# Results: 129 vLLM Token-Generation Benchmark

**Main goal:** Measure vLLM token generation rate  
**Tools:** Start python -m vllm.entrypoints.openai.api_server on port 8000, then run scripts/benchmark_serving.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_141 · recorded 2026-11-14). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× AMD Instinct MI300X VF (196288 MB) · INTEL(R) XEON(R) PLATINUM 8568Y+ · Ubuntu 24.04.5 LTS · kernel 6.8.0-147-generic · driver 7.1.9.31600000
- **Run:** 2026-11-14T11:47:45Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 03:25 · benchmark 00:07 · whole run 04:55
- **Source:** run 129_20261114_114745
- **Command:** `bash run_benchmark.sh --smoke --model-name mistralai/Mistral-7B-v0.3 --dtype bfloat16 --tensor-parallel-size 1 --gpu-memory-utilization 0.9 --input-len 64 --output-len 16 --max-num-seqs 2 --max-concurrency 2`

| # | Metric | Result |
|---|---|---|
| 1 | Generated token rate (output_token_throughput_tokens_sec) | 374.1813380081985 |
| 2 | TPOT, ms (time_per_output_token_tpot_p50_msec) | 4.44644860005307 |
| 3 | Time To First Token, ms (ttft_p50_msec) | 13.608402999125246 |
| 4 | ITL, ms (inter_token_latency_itl_p50_msec) | 4.677515000366839 |
| 5 | End-to-end request latency p50, ms (end_to_end_request_latency_msec) | 80.30513199992129 |
<!-- /profile:smoke -->
