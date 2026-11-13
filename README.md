# Voxlexis — Language Pronunciation & Speech Trainer

**Voxlexis** is an experimental automated speech recognition (ASR) platform designed for targeted pronunciation training, phoneme accuracy scoring, and language skill acquisition (specifically tailored for tonal language learning such as Mandarin Chinese).

---

## 1. Core Capabilities

- **Phoneme Accuracy Scoring**: Compares spoken audio against reference phonetic models using forced alignment (e.g. Wav2Vec2-XLSR / Whisper-based phoneme extraction).
- **Tonal Contour Visualization**: Analyzes fundamental pitch frequency ($F_0$) to provide real-time visual feedback on pitch contour accuracy for Chinese tones (1st through 4th tones + neutral tone).
- **Targeted Evolution Loop**: Pinpoints specific problematic phonetic pairs, generates custom drills, and tracks objective pronunciation improvement over time.

---

## 2. Architecture & Pipeline

```
Microphone Input
       │
       ▼
Audio Normalization & Silence Trimming (16kHz mono WAV)
       │
       ├───▶ Pitch Tracking Engine (PYIN / Crepe) ──▶ Pitch Contour ($F_0$) vs Reference
       │
       └───▶ Phoneme Alignment & CTC Loss Model ──▶ Phoneme Confidence & Error Breakdown
                                                           │
                                                           ▼
                                               Objective Accuracy Score (0-100%)
                                               + Actionable Correction Guidance
```

See [`GOALS.md`](./GOALS.md) for the phased milestones and pedagogical roadmap.
