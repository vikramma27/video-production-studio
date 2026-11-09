# Production Operations and Human Approval

## Episode state machine
IDEA → RESEARCHED → SCRIPT_DRAFT → SCRIPT_APPROVED → CAST_LOCKED → STORYBOARDED → AUDIO_READY → SCENE_BUILT → RENDERED → EDITED → QA_APPROVED → READY_FOR_UPLOAD → PUBLISHED.

Only the user approves scripts, character/voice/brand locks and final videos. Agents may recommend transitions but cannot bypass approval.

## Approval gates
- G1: reference benchmark and creative direction.
- G2: character concepts, turnarounds, expression/body-action samples and playable pilot.
- G3: voice auditions and narration sample.
- G4: channel names/handles, icons, banner and brand system.
- G5: thumbnail grammar and sample variants.
- G6: content ideas and calendar.
- G7: batch storyboard and representative renders.
- G8: complete final playback and upload package.

Store user decision, asset/version hashes, date, notes and superseded version. Frozen assets are immutable; revisions branch.

## Durable jobs
Every stage writes manifests, input/output hashes, version pins, logs, status, timestamps, retry count and QA. Resume only invalidated stages. After two failures using the same method, stop and diagnose.

## Batch production
User selects one or two weeks. Build dependency graph; parallelize independent preparation; schedule GPU work under measured resource limits; checkpoint at shot and episode boundaries. User may leave laptop open for long batches. Queue survives restarts.

## Delivery
Video, thumbnail, captions, title/description suggestions, rights/provenance manifest, voice/music licence notes, render report, editorial QA and suggested upload slot. User publishes manually.

## Privacy and rights
No upload of private scripts, voice samples, character assets or reference footage to hosted services without explicit approval. Use only authorized voice samples. Review software, model, music, sound, font and asset licences separately. Reference media never enters final output.