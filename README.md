# CloudGPU Agent Compute Layer

Agent Skills for discovering GPU compute, comparing task fit, requesting an explicit quote approval, running bounded work and exporting results. For developers outside mainland China only; see https://cloudgpu.app/terms.

## Skills

- `cloudgpu-discover-compute`: discover live GPU capabilities and compare workload requirements.
- `cloudgpu-lora-finetune`: plan approved LoRA / QLoRA training and retrieve checkpoints.
- `cloudgpu-comfyui-images`: prepare reviewed ComfyUI workflows and export images.
- `cloudgpu-ai-short-drama`: plan open-model video stages with a project budget and review gates.
- `cloudgpu-open-model-inference`: plan GPU inference and evaluation with protected inputs and verified outputs.

## Install

Download this repository's source archive from GitHub and extract it. From the extracted repository directory, copy a selected skill into your client's skills directory:

```sh
mkdir -p ~/.agents/skills
cp -R cloudgpu-discover-compute ~/.agents/skills/
```

Repeat for other skills you need. Follow your client's current Agent Skills loading instructions and reload if required. Format compatibility is not a claim that every client has been tested.

## Workflow and safety

1. Read https://cloudgpu.app/docs/agents and https://cloudgpu.app/openapi.json for the current contract.
2. Discover live GPU capabilities and request a quote before paid work.
3. Present workload, data permissions, cost estimate and hard time/spend limits for explicit user approval. Connecting an account does not approve a job.
4. Supply a reviewed workload command, pinned dependencies, compatible licensed models, authorized inputs and acceptance checks before execution.
5. Download and verify outputs before destroying an interactive instance, or explicitly save them to Workspace / configured Job output storage and verify the saved result. Instance disks are erased on termination. Retention, funded-account access, storage budgets and output limits are separate from GPU rental; check the current contract before promising persistence.

The skills describe documented interfaces, not pretested end-to-end workload recipes. No paid GPU execution or model generation was performed to validate them. Keep credentials in a secure client credential mechanism; never include secrets in chat, source or logs.

## REST and MCP

REST documentation: https://cloudgpu.app/docs/agents

MCP documentation: https://cloudgpu.app/docs/mcp

The MCP server is available as a separate local stdio package:

```sh
npx -y cloudgpu-mcp
```

For remote clients, `https://cloudgpu.app/mcp` is the Streamable HTTP endpoint with OAuth. Follow the current MCP documentation for authorization and the transport-specific tool list. For local stdio, use `connect_account` and `finish_connect` or your client's secure credential mechanism. These skills do not bundle the MCP server; connecting does not approve paid work.

## Billing

GPU rental uses source-specific billing: minute-billed sources round partial minutes up; whole-hour sources have a one-hour minimum and charge each started hour in full, including an early voluntary stop. Obtain a current quote, show its minimum charge, billing increment and start condition, and obtain explicit approval before allocation. Do not infer billing from a GPU model or hourly rate. Storage has separate budgets, usage charges and retention terms; consult the current API contract.

## License

MIT. See LICENSE. Model, dataset and third-party workflow licenses remain separate.
