# Global Reference Audit

## Purpose

This repository serves as the enforcement source for canonical naming and terminology across the current editable corpus.

## Canonical vocabulary

- Active project: `CeloHT`
- Canonical GitHub organization: `Celo-HaiTi`
- Canonical stable-value currency terminology: `USDm`
- Obsolete project name: `Celo-HT`
- Obsolete currency term: `cUSD`

## Mandatory current-corpus rule

CURRENT CORPUS REQUIREMENT:

The current editable repository corpus must use only canonical active terminology. Obsolete terminology must not be retained merely because it appears in historical context. Immutable Git history is excluded from this requirement.

The audit therefore fails if current editable files contain:

- `cUSD`
- `Celo-HT`
- obsolete `Celo-HT` GitHub URLs

Historical Git history may retain obsolete terminology, but current editable files must follow the canonical vocabulary.

## Scope distinction

### Immutable history

Allowed to contain old terminology because rewriting Git history is outside the scope of normal documentation cleanup.

Examples:

- old commits
- commit messages
- immutable commit hashes
- historical Git objects

### Current editable corpus

Must follow canonical terminology.

Examples:

- current README files
- current Markdown files
- current source files
- current documentation
- current configuration
- current website content
- current examples
- current links
- current changelogs

The second category must have ZERO obsolete visible terminology.

## Enforcement standards

1. Treat `cUSD`, `Celo-HT`, and obsolete `github.com/Celo-HT/...` URLs as current corpus violations.
2. Do not classify them as acceptable simply because they are historical references inside current files.
3. Do not preserve obsolete terms in current documentation by labeling them as historical if a neutral rewrite is possible.
4. Rewrite the meaning without exposing the obsolete term whenever technically safe.
5. Preserve compatibility only when a live code identifier or API contract truly requires it; document the exception explicitly rather than leaving the obsolete term in current user-facing text.
6. Never alter the canonical forms `CeloHT` or `Celo-HaiTi`.

## Workflow

For every occurrence:

1. Identify the repository.
2. Identify the file and line.
3. Determine whether it is current terminology, historical wording, a URL, code identifier, compatibility field, generated output, or another case.
4. Apply the smallest correct change.
5. Preserve functionality and technical compatibility where required.
6. Record any remaining exception as a clearly documented technical exception.

## Outcome

The expected result for current editable files is:

- `cUSD` → zero matches
- `Celo-HT` → zero matches
- `github.com/Celo-HT/` → zero matches
- `github.com/Celo-HT` → zero matches

Canonical terms remain valid:

- `CeloHT`
- `Celo-HaiTi`
- `USDm`

This audit is authoritative for the current editable corpus. It does not rewrite immutable Git history.
