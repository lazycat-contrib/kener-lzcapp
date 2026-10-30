# Kener for LazyCat

Kener v4.1.10 (ghcr.io/rajnandan1/kener) + Redis 7-alpine, packaged as a LazyCat LPK (community store).

## Publication

MiaoMiao community store app 667, APPROVED, version 4.1.10. Build run 41120277188 with mirror delivery verification. LPK 27136 bytes; SHA256 227a3040a2777ea7687f68289573cb82e82dce98658b2d71d4781b00cb0738b6 downloaded independently and matched at submission.

## Notes

- v4 requires Redis for background job queue: two-container manifest (kener + redis with healthcheck), REDIS_URL wired internally.
- KENER_SECRET_KEY via stable_secret; ORIGIN uses {{.S.AppDomain}} template.
- First build accidentally bumped v3.2.4 to v4.1.10 (image version_source auto-update); fixed by adding Redis instead of pinning old version.
- Duplicate check: kener query returned 0 in MiaoMiao before submission (official store has cloud.lazycat.app.kener, different package).
- No smoke job, no file-chooser interceptor. Config checks only; probe scheduling and alert delivery not verified on a live device.
