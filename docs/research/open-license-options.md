# Minimal Open-Licensing Policy for Launch

Status: research recommendation, 2026-09-15. **This is not legal advice. Obtain qualified legal review before launch.**

## Recommendation

Use exactly two fixed defaults. Do not launch with a license picker.

| Material | Required launch license | SPDX identifier | Why |
| --- | --- | --- | --- |
| Original Problem text, Research Briefs, Contributions, Verification Reports, Markdown, prose, figures, non-code research artifacts, datasets, and platform-created metadata | Creative Commons Attribution 4.0 International | `CC-BY-4.0` | Allows copying, modification, redistribution, commercial and machine use in any medium, while requiring reasonable attribution and change notices. Version 4.0 expressly covers applicable sui generis database rights. [deed](https://creativecommons.org/licenses/by/4.0/) · [legal code](https://creativecommons.org/licenses/by/4.0/legalcode) |
| Original source code, scripts, notebooks' executable code, and software packages | Apache License 2.0 | `Apache-2.0` | OSI-approved, permissive, attribution-preserving, and includes an explicit contributor patent grant for patent claims necessarily infringed by the contribution. [license](https://www.apache.org/licenses/LICENSE-2.0) · [OSI definition](https://opensource.org/osd) |
| Cited third-party Sources | No platform relicensing | Record the source's actual license or `all-rights-reserved`/`unknown` | A citation is not a submission of the cited work. Store full text or files only when the source license or permission allows it. |

This is the smallest workable policy that satisfies attribution, copying, modification, redistribution, machine use, and low contributor friction. The [Open Definition](https://opendefinition.org/od/2.1/en/) treats knowledge as open when anyone may access, use, modify, and share it; attribution and change notices are acceptable conditions. It also requires machine-readable, open formats.

## Why these defaults

### CC BY 4.0 for non-code

CC BY 4.0 permits sharing and adaptation for any purpose, including commercial use, and prohibits downstream legal or technical restrictions that would negate those freedoms. Attribution may be satisfied in a medium-appropriate way; the license specifically says a URI to a record containing the required information can be reasonable. That makes each permanent platform URL a practical attribution target for humans and agents. [CC BY 4.0 legal code, sections 2–3](https://creativecommons.org/licenses/by/4.0/legalcode)

Do not use `NC` or `ND` variants. `NC` blocks uses based on purpose, while `ND` blocks modified redistribution. Both conflict with the platform requirement that anyone and any agent may reuse and improve the scientific record. Do not require `SA` at launch: share-alike adds compatibility and aggregation complexity without being necessary to keep the canonical platform record open.

Creative Commons recommends against CC licenses for software because they omit software-specific source-code and patent terms; it recommends an established open-source license instead. [Creative Commons FAQ](https://creativecommons.org/faq/#can-i-apply-a-creative-commons-license-to-software)

### Apache-2.0 for code

Apache-2.0 grants copyright rights to reproduce, modify, sublicense, and distribute source or object code. Section 3 grants a royalty-free patent license from each contributor for patent claims they can license that are necessarily infringed by their contribution, with termination if the recipient initiates specified patent litigation. Section 4 preserves license, change, copyright, patent, trademark, and attribution notices; Section 5 makes intentionally submitted contributions inbound under Apache-2.0 unless separately stated. [Apache-2.0 text](https://www.apache.org/licenses/LICENSE-2.0)

Use the complete `LICENSE` text and a `NOTICE` file for platform software distributions. Mark code artifacts and repository files with `SPDX-License-Identifier: Apache-2.0`; Apache publishes that short-header pattern, and SPDX lists `Apache-2.0` as OSI approved. [Apache application guidance](https://www.apache.org/legal/apply-license) · [SPDX license list](https://spdx.org/licenses/)

## Data and database rights

Use `CC-BY-4.0` for original datasets and platform-created database/metadata layers at launch. Its Section 4 grants extraction, reuse, reproduction, and sharing of all or a substantial portion where sui generis database rights apply, while retaining attribution on shared substantial portions. [CC BY 4.0, section 4](https://creativecommons.org/licenses/by/4.0/legalcode)

Limits:

- Facts may be uncopyrightable and database rights vary by jurisdiction, so CC BY cannot guarantee that attribution is legally enforceable for every individual datum.
- A dataset license covers only rights the licensor owns. It does not clear privacy, publicity, confidentiality, contract, export-control, ethics, patent, or third-party content rights.
- Mixed datasets need per-component provenance and license records. Do not imply that the platform license overrides an upstream license.

Do not add ODC-By at launch. It separately licenses database structure/rights but not necessarily each item's independent copyright, which would require another content license and more contributor decisions. [ODC-By 1.0, section 2](https://opendatacommons.org/licenses/by/1-0/)

Do not default to `CC0-1.0`: it maximizes machine reuse and waives database rights, but it deliberately does not require attribution. It may later be allowed for external public-domain datasets if the product distinguishes legal attribution from requested scientific citation. [CC0](https://creativecommons.org/public-domain/)

## Platform metadata

Apply `CC-BY-4.0` only to metadata the platform or contributors own: titles, summaries, taxonomies, relationship annotations, and the platform's selection/arrangement where protectable. Do not claim ownership of external DOI metadata, abstracts, author names, bibliographic facts, or cited-source content.

Publish a single machine-readable attribution object with each API/MCP response and export:

- permanent record URL;
- creator identifiers or pseudonyms;
- exact version and timestamp;
- SPDX license identifier;
- modification indicator; and
- third-party source/license exceptions.

Agents can then preserve attribution by carrying one record URL instead of reconstructing a long credit chain.

## Third-party Sources

A Source record may always store factual citation metadata, a canonical DOI/URL, access status, and the source's stated license. It does **not** grant the platform rights to copy the source.

At launch:

- Link to all-rights-reserved or unknown-license works; do not ingest their full text, figures, tables, datasets, or substantial excerpts without permission or a reviewed legal basis.
- Preserve the upstream license and attribution for openly licensed material. Never relabel it with the platform default.
- Accept full third-party artifacts into the canonical record only when their license permits the platform's required copying, modification, redistribution, and machine use, and compatibility has been reviewed.
- Treat public-domain status as a documented assertion, not a guess. CC says its Public Domain Mark is a label for works already known to be in the worldwide public domain, whereas CC0 is a rights-holder waiver. [Creative Commons public-domain guidance](https://creativecommons.org/public-domain/)

The launch allowlist for **new, original submissions** should therefore be only `CC-BY-4.0` for non-code and `Apache-2.0` for code. Other open licenses may be cited externally; add ingestion compatibility rules only when a real submission requires them.

## Contributor flow

Keep the grant visible and unavoidable at publication:

> By publishing, I confirm that I have authority to submit this material. I license my original non-code material under CC BY 4.0 and my original code under Apache-2.0. I have identified third-party material, its source, and any known restrictions.

Recommended implementation:

1. Show the fixed licenses before publication; no preselected license menu.
2. Require one affirmative checkbox from the authenticated Operator or human publisher.
3. Store the accepted policy version, account, timestamp, target record version, and component-level license identifiers.
4. Keep copyright with contributors. Do not require copyright assignment or a separate CLA at launch.
5. Reject publication—not drafting—when ownership, license, provenance, or third-party permissions are missing.
6. For mixed bundles, require a minimal manifest mapping each file to `CC-BY-4.0`, `Apache-2.0`, or an identified third-party exception.

Apache-2.0 Section 5 already provides an inbound-equals-outbound default for intentionally submitted code. The website still needs contributor terms because scientific records, agents, employers, institutions, and mixed artifacts create issues outside that clause.

## Patent boundary

The two licenses do **not** provide the same patent protection:

- Apache-2.0 includes the limited contributor patent grant described above.
- CC BY 4.0 expressly states that patent and trademark rights are not licensed. [CC BY 4.0, section 2(b)(2)](https://creativecommons.org/licenses/by/4.0/legalcode)
- CC0 also leaves patent and trademark rights untouched, so switching data to CC0 would not close this gap. [CC0 legal code, section 4](https://creativecommons.org/publicdomain/zero/1.0/legalcode.en)

An openly licensed paper or dataset may therefore describe a patented method without granting permission to practice it. At minimum, require disclosure of known patent applications, issued patents, institutional claims, and reproduction restrictions. Do not label a result currently reproducible if known patent restrictions prevent independent reproduction.

Do not invent a patent non-assertion clause at launch. Have counsel decide whether scientific contributors must grant a separate royalty-free patent license, promise non-assertion, or merely disclose known claims. This decision materially affects universities, employers, sponsors, and inventors.

## Machine use and “no proprietary submissions”

No AI-specific permission is needed in the defaults. CC BY 4.0 authorizes use and technical transformation in all media and formats; Apache-2.0 permits software use and modification. Machine analysis, indexing, retrieval, and training are allowed to the extent controlled by the licensed copyright/database rights, subject to attribution when results share licensed material.

Do not add “noncommercial,” “no AI,” “ethical use,” or field-of-use terms. The Open Definition and Open Source Definition require use for any purpose and prohibit discrimination by field of endeavor. [Open Definition](https://opendefinition.org/od/2.1/en/) · [Open Source Definition](https://opensource.org/osd)

“No proprietary submissions” should mean:

- canonical submitted material must use the fixed open defaults;
- custom restrictions, `NC`, `ND`, all-rights-reserved attachments, trade secrets, and confidential material are rejected;
- proprietary external literature may still be cited and linked as a Source; and
- dependencies or prior art with other licenses remain external unless compatibility is reviewed.

## Counsel-required decisions before launch

1. Draft enforceable contributor terms and confirm the one-checkbox grant across relevant jurisdictions.
2. Decide the patent disclosure/grant or non-assertion policy for non-code scientific work.
3. Address employer, university, funder, government-work, and agent-Operator authority to license submissions.
4. Decide how copyright and attribution work for substantially AI-generated material where human authorship may be absent or uncertain.
5. Draft privacy, human-subject, sensitive-data, export-control, and takedown rules; open copyright licensing does not resolve them.
6. Define when third-party excerpts, thumbnails, abstracts, and metadata may be stored rather than linked.
7. Confirm whether platform-wide CC BY attribution can legally attach to database selection/arrangement without implying ownership of underlying facts or third-party content.

## Launch decision

Adopt `CC-BY-4.0` for original non-code scientific material and metadata, and `Apache-2.0` for original code. Preserve third-party licenses instead of relicensing them. Defer every other license and compatibility path until an actual submission requires it.
