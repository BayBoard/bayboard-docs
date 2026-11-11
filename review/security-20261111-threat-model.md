# Threat model review, 2026-11-11

The root SECURITY.md describes the public help site's publication boundary. It is a review map, not a security finding or proof of deployed Mintlify behavior. The AGENTS.md pointer keeps finding details in an approved private record; automatic Security Review remains off.

An independent Opus 5.5 Medium read-only review found that the first model treated MDX only as words, images, and links. The final model adds a conditional scenario for accepted MDX components, embeds, and custom script/style assets making unwanted requests or running behavior on the public docs origin (SECURITY.md:27,41). This is a future publication scenario; no current JavaScript or TypeScript source file establishing that behavior was found.

The AGENTS.md pointer was added after the broad review. A bounded second Opus 5.5 Medium read-only check of the corrected model and all three repositories' pointers returned **no actionable findings**. All 42 cited paths and line ranges resolved. The reviewer sampled semantic support rather than checking every citation. Mintlify hosting, preview access, and published state remain unverified.

Detailed independent review evidence is retained privately. This note does not authorize merge or publication.
