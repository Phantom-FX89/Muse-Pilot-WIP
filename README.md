# 🔬 Muse-Pilot (Work in Progress)

**Muse-Pilot** is an AI-assisted music production platform exploring machine learning-driven composition, arrangement, and sound design.

## Vision
Explore the intersection of deep learning and creative music production, building tools for intelligent sound design and composition assistance.

## Current State
- **Phase 1**: Audio processing and ML feature extraction pipelines
- **Phase 2**: Experimental model architectures (VAE, GAN, Transformers)
- **Phase 3**: Real-time interactive generation and synthesis

## Tech Stack
- **Audio Processing**: librosa, scipy.signal, PyTorch Audio
- **ML Framework**: PyTorch with custom training loops
- **Frontend**: React with Web Audio API
- **Deployment**: Docker + FastAPI

## Active Experiments

### 1. Mel-Spectrogram Variational Autoencoder
- Learns latent representations of musical timbres
- Enables smooth interpolation in learned space
- 128-dim bottleneck with β-VAE training

### 2. Harmonic-Percussive Source Separation
- Decompose polyphonic audio into harmonic/percussive components
- Uses median filtering in time-frequency domain
- Enables independent processing of melodic and rhythmic elements

### 3. Sequence-to-Sequence Arrangement Model
- LSTM-based encoder-decoder for musical suggestions
- Input: Chord progression and melody
- Output: Suggested arrangements and instrumentation

### 4. Real-time Synthesis Backend
- Optimized inference for sub-100ms latency
- Multi-GPU inference pipeline
- Streaming audio generation for live performance

## Architecture Overview

```
Audio Input
    ↓
    [Feature Extraction] → Mel-Spectrograms, MFCCs, Chroma
        ↓
        [Representation Learning] → VAE/GAN latent space
            ↓
            [Sequence Modeling] → LSTM/Transformer predictions
                ↓
                [Synthesis] → Learned decoder → Audio Output
                ```

                ## Key Learnings
                - Spectral distance metrics better for perceptual evaluation than raw MSE
                - β-VAE crucial for preventing posterior collapse
                - Ensemble methods improve generalization across musical styles
                - Real-time constraints require aggressive model compression

                ## Next Steps
                1. Improve GAN training stability with Wasserstein loss
                2. Implement differentiable DSP for end-to-end optimization
                3. Add interactive latent space explorer (web UI)
                4. Explore multi-modal learning (audio + MIDI + text)
                5. Build reinforcement learning layer for composition optimization

                ## Methodology
                - **Hypothesis-Driven**: Test specific hypotheses with controlled experiments
                - **Iterative Development**: Rapid prototyping and evaluation
                - **Listening Tests**: Subjective evaluation with perceptual metrics
                - **Ablation Studies**: Understand component contributions

                ## Contributing
                This is an active research project exploring AI in music production.

                ## License
                MIT License
