# FRAME X STUDIO — Senior Full-Stack Audit

## Fixed
- GSAP HTMLCollection warning: converted `grid.children` to `Array.from(...)`.
- Resilient Lenis initialization when GSAP CDN is unavailable.
- WebGL renderer fallback for unsupported devices; disabled `preserveDrawingBuffer` and capped pixel ratio.
- Removed duplicate video attributes in the work strip.
- Portfolio videos use `preload="none"` so all 9 do not download immediately.
- Localized embedded base64 media into `assets/media/` to dramatically shrink initial HTML payload.
- Added Vercel security headers: CSP, nosniff, frame protection, referrer policy, permissions policy, COOP.
- Added preconnect hints for CDN dependencies.
- Added lazy/async thumbnail decoding.

## Notes
- Third-party libraries are still loaded from pinned HTTPS CDN URLs (GSAP 3.12.5, Lenis 1.1.14, Three.js r128). Self-hosting them would further reduce supply-chain risk, but network access was unavailable during this audit, so no integrity hashes were invented.
- The Chrome `file://` origin warning shown during local testing is a browser local-file security behavior; production Vercel HTTPS hosting is the correct environment for final verification.
