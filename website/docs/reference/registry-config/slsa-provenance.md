---
sidebar_position: 2100
---

# slsa_provenance

- `aqua > v1.26.0`

Please see [Cosign and SLSA Provenance Support](/docs/reference/security/cosign-slsa) too.

## Fields

- type (string): `github_release` or `http`
- repo_owner (string) (optional):
- repo_name (string) (optional):
- url (string) (`http` requires):
- asset (string) (`github_release` requires):
- signer_identity (string) (optional): Expected Fulcio certificate URI subject
- signer_issuer (string) (optional): Expected OIDC issuer

`signer_identity` and `signer_issuer` provide metadata for registry consumers that
verify signing certificates directly, such as mise. Set both to the exact values
expected from the publisher's signing workflow. Aqua delegates verification to
`slsa-verifier`, using the source repository and tag.

e.g.

```yaml
slsa_provenance:
  type: github_release
  asset: multiple.intoto.jsonl
```
