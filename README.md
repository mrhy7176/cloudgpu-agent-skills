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
5. Download and verify outputs before destroying an interactive instance. A batch command must export results to user-authorized storage before exit. Platform disks are erased on termination; native retained artifacts are not available.

The skills describe documented interfaces, not pretested end-to-end workload recipes. No paid GPU execution or model generation was performed to validate them. Keep credentials in a secure client credential mechanism; never include secrets in chat, source or logs.

## REST and MCP

REST documentation: https://cloudgpu.app/docs/agents

MCP documentation: https://cloudgpu.app/docs/mcp

The MCP server is a separate local stdio package:

```sh
npx -y cloudgpu-mcp
```

Configure it through your MCP client's secure credential mechanism. The website `/mcp` path is not a remote MCP endpoint. These skills do not bundle the MCP server.

## Billing

Billed per minute, partial minutes count as a full minute, billing stops on destroy.

## License

MIT. See LICENSE. Model, dataset and third-party workflow licenses remain separate.
