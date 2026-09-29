Garak ( LLM Vulnerability scanner ) by NVIDIA.

Security scanner for an LLM.

Send many Adversarial prompts to model and checks the responses for weakness.

### Setup:
```
python3 -m venv garak
source garak/bin/activate
```
```
Garak
  ________________________
 |                        |
Attack Prompt        Detectors
 |                        |
LLM  ----------> Analyze Response
 |
Vulnerabilities
[ prompt  injection,
Jailbreak,
Encoding attacks,
Data Leakage tests,
Toxicity Tests,
Hallucinatin tests,
Other probs ]
```

Export Environment variable:
```
export OPENAICOMPATIBLE_API_KEY="dummy"
```

garak-vllm.yaml

```YAML
plugins:
  generators:
    openai:
      OpenAICompatible:
        uri: "http://xx.xx.xxx.xx:8001/v1/"    ## this is the URL of custom Model endpoint.
```
Run:
```
garak   --config ~/garak-vllm.yaml   --target_type openai.OpenAICompatible   --target_name qwen3.5-122b-a10b   --spec probes.promptinject
```

With Specific probes:
```
garak \
  --config ~/garak-vllm.yaml \
  --target_type openai.OpenAICompatible \
  --target_name qwen3.5-122b-a10b \
  --spec probes.promptinject
```

