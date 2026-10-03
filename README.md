# QuestionPunk for Hermes Agent

Install the public package, inspect it, and enable its four research skills:

```sh
hermes plugins install questionpunk/hermes-plugin --no-enable
hermes plugins show questionpunk
hermes plugins enable questionpunk
```

Merge the supplied `config-merge.json` into your profile's `config.yaml` with its normal configuration controls. Preserve existing settings. The JSON object is also valid YAML; do not replace the whole config file. It defines `mcp_servers.questionpunk` with the canonical HTTPS endpoint, OAuth, and `read write responses:read` scopes. The explicit profile entry takes precedence over the portable package's server of the same name. This is deliberate: Hermes' portable MCP adapter does not carry the native `auth: oauth` option.

```sh
hermes mcp login questionpunk
hermes mcp list
```

Authorize your own QuestionPunk account in the browser. Tokens stay in Hermes' private profile credential store. Start a new session and ask: “Use QuestionPunk to create a QA draft with one onboarding feedback question, then read it back. Do not publish it.” Verify the saved questions in QuestionPunk. Tool names use `mcp__questionpunk__` prefixes; the skills resolve their base names.

Read/write permission allows research authoring, including publication when requested. Response data requires the additional `responses:read` grant. Do not share one profile or bearer token between unrelated users. A directory listing is separate from this direct GitHub installation.

Sources checked October 3, 2026: [portable plugins](https://hermes-agent.nousresearch.com/docs/developer-guide/plugins), [MCP and OAuth](https://hermes-agent.nousresearch.com/docs/user-guide/features/mcp). Host version, authentication, and workflow results must be recorded separately from structural validation.

## Connection for this build

MCP endpoint: https://app.questionpunk.com/api/v1

QuestionPunk: https://app.questionpunk.com
