# Voice Identity and Narration Approval System

## Candidate platform
The likely project the user remembers is [Jamie Pine's Voicebox](https://github.com/jamiepine/voicebox), a local-first open-source voice studio. It is an evaluation candidate, not yet installed or selected. Its current documentation describes several local engines including Qwen3-TTS, Qwen CustomVoice/VoiceDesign, Chatterbox Multilingual/Turbo, HumeAI TADA and Kokoro.

The Voicebox application licence and each model/weight licence are separate. Verify commercial-use rights, language support, watermark/output terms and hardware needs for the exact engine and weights. Existing Chatterbox and IndicF5 evaluations remain in scope. Benchmark Qwen3-TTS and other candidates only when they improve quality, consistency, language support or licence clarity.

## Voice audition workflow
Create an original voice identity per channel. Generate multiple auditions across suitable age impression, gender presentation, accent, warmth, pitch, pace, texture, energy and emotional range. Use identical test scripts: neutral intro, excited hook, suspense, sadness, anger, conversational dialogue and a longer narration paragraph. Provide playable samples and a comparison sheet. User selects and iterates.

## Voice profile lock
Record voice ID/channel ownership, engine and exact model/weights revision, runtime/settings, reference sample provenance and consent, language/accent, pitch/rate/style, pronunciation dictionary, audition samples, licence review, frozen version and approval timestamp.

Use only voices owned, explicitly authorized or properly licensed. Never clone or imitate reference-channel narrators or an identifiable person without authorization.

## Consistency
Each episode pins a frozen voice-profile version. Keep model, weights, runtime and settings fixed. If an update changes timbre, run comparison samples and require approval before changing the canonical voice. Preserve prior versions for reproducibility.

## Production and acceptance
Batch narration, transcribe/time locally with faster-whisper, check loudness/clipping/silence/pronunciation, regenerate only affected segments and preserve provenance. Acceptance requires multiple playable auditions per channel, same test script, repeatability checks, local runtime benchmark, exact licence review and explicit user approval.