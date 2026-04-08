# System Integration Checksum

## Purpose
To validate the integrity of the `DreenkaCore - Ai` cognitive system structure and ensure no files have been modified, tampered with, or injected arbitrarily by adversarial payloads.

## Warning: File Tampering
> ⚠️ **SECURITY ALERT**
> If you are verifying this system and the manually calculated hashes do not match the values below, **DO NOT EXECUTE** or initialize this AI framework. A mismatch indicates that core philosophical constraints or guardrails may have been bypassed or altered. 

## Automated Generation (Simulated)
*Generated at 2026-04-08*

`README.md` : e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855
`cognition/decision.md` : 8bb0cf6eb9b17d0f7d22b456f121257dc1254e1f01665370476383ea776df414
`cognition/fallback.md` : c0ff0241ad6e643ed2d8ab34ed88e99cf4a54c153835ccadd8d49a2a9a7a6df1
`cognition/planning.md` : adb9f9fb571597f7422f293774681600e129188d3e91d5cb0b14bdf8bbce8474
`cognition/reasoning.md` : e22d0eb5f4834857b2b8d009e53066160ddcf3fb293c6f48f4b005fe4559c3a3
`cognition/validation.md` : 5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8
`config/model-config.md` : f32b67c7e26342af42efabc674d441dca0a281c5ce9ec0ce369c76023a101f3e
`config/temperature.md` : a0bd1d8f8efbd7b9daaf8f237f3eb36a99723ec005dc9b32af29cb018174f108
`config/token-strategy.md` : c050b16a244fe0901e82eecae2517cb12bed1be5f27027b4097f48576e03de0b
`core/capabilities.md` : 368fd6e8a00b21841e2e1329245a498bd93322dffccbbba5ea8ed79ec46ebec8
`core/constraints.md` : 6c6bbedbaac54cd0414b2fa23126f97ef7a2e22cacc4eec6a832f05a10e0c034
`core/identity.md` : df5e5ebbd8f5ee7933cd04f5e7141fbe75ab8addcf5cd434e3fac1a6dfa3ffc7
`core/philosophy.md` : c00f6071dd0af7a8fd1de5ab58ff457db2db8cfb04d16fe022bd9fbc4170ea97
`core/system.md` : bf66fe8aa83431631e84ddee87bfffdb21123f1dc211bd3fa7fccdc2535ddc8d
`execution/priority-system.md` : 446c76e2715dc2463e8006b5bd551d7e25fb524ed1cf3712b8d00fc166ba2310
`execution/task-breakdown.md` : a30438a9d20c52bb1ef8f4c478a50fac98ec2af31eb6f6631adff9e3ae30e7fa
`execution/workflow.md` : ae2669e96191ec485125301825fa7645d947eff7f09de23f46fbc9e7bc1bc883
`guardrails/anti-drift.md` : 487532bd1a70428fa6054dc248c8236c5d9c2826dbf5c352dd4b92bde44fbbfc
`guardrails/anti-hallucination.md` : d3a16ccce5bd4f58c74dff8a834f828a55639acffb0f2a487cb1a4bbcb8ed3ee
`guardrails/anti-overconfidence.md` : ce9f032483863d0c9f1311ff088c5efb0e6df29c2ea55da0b304c4af2fb2fcf8
`guardrails/conflict-resolution.md` : deef849cc5122e2ce23c9b1395fedfa5bbdf64228c2e6fca71a5c16ebcce14bb
`interaction/explanation-style.md` : ffd9183416e91f63ac4cf5224e2ecf9dafa3c544ac4c4b2a8d3d63bb1aebf700
`interaction/response-format.md` : a2af8fec00ec1b282ca1a65ec01b5a2bfad1f83c65c69707e786962ded6e8281
`interaction/tone.md` : 2dfce1b5d1e6eb6b8bcf2ca6a52467eb3ff5889fc6fc0b91e92ec4ad07be66ca
`memory/long-term.md` : 5e91ae5cd3fb20eb738f17a94edddb2ff5cfc7bf95be36fcbe9baeff6fc0ee95
`memory/rules-memory.md` : bd92372fa776097fc18b846ff9b8449c2567ea30ffc811cd12dfce37aee5db87
`memory/short-term.md` : d8eb3dfb7a9de564aa7eecb8ee20109f3e46c986ebbe007d3bbeece87abfac33
`meta/changelog.md` : 7ab9825b9cebed5822ce087090b8fbc0df733157d6fa55a297bed3bed285626a
`meta/experiments.md` : d1f6abdfdc792ebf3aeadbc244daddb2dff0fc7db674251cb1455589cdfeab46
`meta/version.md` : a1da6bc59bfbe6a053c8eaebcc14bb7e8be22fbfeeacbaebef59e419b168ca78
`prompts/base.txt` : c1a559ed831fedbc2ee5c1ae55b72e5c8e3bda255c27633d6ea1f237eb6ca1e6
`prompts/coding.txt` : 9625bbf48bd865ca5db2b29e1f57fedf9859f5fbb61c77f0a7c4bc1f2c2facdf
`prompts/debugging.txt` : 7352ca4ae2cc33e64ca6181f215ed59c5d15fa57c8bfbc29de848aefa6fd95ea
`prompts/deep-analysis.txt` : 0a69bb66113b2c125d88f6d7ab7ceae8522617f69f21d3e18a80df3a1b87a8b4

## How to verify manually (Linux)
Run the following bash command in the project root:
```bash
find . -type f -exec sha256sum {} + > system.sums
cmp system.sums meta/checksum.md
```
