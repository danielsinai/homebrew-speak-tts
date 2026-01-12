# speak-tts

Voice cloning CLI for Mac (Apple Silicon) using F5-TTS.

## Installation

### Via pipx (recommended)

```bash
pipx install git+https://github.com/danielsinai/speak-tts.git
```

### Via pip

```bash
pip install git+https://github.com/danielsinai/speak-tts.git
```

## Requirements

- macOS with Apple Silicon (M1/M2/M3/M4)
- Python 3.10+

## Usage

### Add a Voice Profile

```bash
speak --add-profile daniel --voice ~/voice.wav --text-file ~/reference.txt
```

The reference audio should be a clear WAV recording (24kHz) of the voice you want to clone, and the text file should contain an exact transcript.

### Generate Speech

Plays audio directly (no file saved):

```bash
speak daniel "Hello, this is a test!"
```

Save to a file:

```bash
speak daniel "Hello world" --output ~/Desktop/hello.wav
```

### List Profiles

```bash
speak --list
```

### Play Audio

```bash
speak --play output.wav
```

## Profile Storage

Profiles stored in `~/.speak/profiles/<name>/` with:
- `reference.wav` - Voice sample
- `reference.txt` - Transcript

## Tips

- **Reference Audio**: 5-15 seconds, 24kHz, minimal background noise
- **Reference Text**: Exact transcript of the audio
- **First Run**: Downloads F5-TTS model (~1GB)

## Development

```bash
git clone https://github.com/danielsinai/speak-tts
cd speak-tts
python3 -m venv venv
source venv/bin/activate
pip install -e .
speak --help
```

## License

MIT
