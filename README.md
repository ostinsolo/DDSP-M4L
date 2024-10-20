# M4L DDSP Timbre Transfer

This Max for Live device connects [DDSP](https://github.com/magenta/ddsp)'s timbre transfer capabilities with Ableton Live, using Google Drive's API for file sharing and Google Colab for processing.


## Features

- Supports five instruments: Violin, Trumpet, Flute, Flute2, & Tenor Saxophone
- Uses Google Colab's GPU for processing
- Integrates with Google Drive for file transfer

## Setup

1. Install Python and pip if not already installed.

2. Install required packages:
   ```
   pip install -r requirements.txt
   ```

3. Set up Google Drive API:
   - Follow [these instructions](https://pythonhosted.org/PyDrive/quickstart.html#authentication) to get an API key.
   - Save the API key as `client_secrets.json` in the same folder as `drive-sync.py`.

4. Initialize the Google Drive folder:
   ```
   python drive-sync.py --init True
   ```
   This creates a 'M4L-Timbre-Transfer-Folder' in your Google Drive root.

5. Open the [notebook in Google Colab](https://colab.research.google.com/github.com/ostinsolo/DDSP-M4L/blob/main/m4l_timbre_transfer.ipynb).

6. In Colab:
   - Set runtime to GPU: Runtime > Change runtime type > GPU
   - Run all cells
   - The last cell starts a loop looking for files to process

* [PyDrive](https://pythonhosted.org/PyDrive/) - for Google Drive access
* [PythonOsc](https://github.com/attwad/python-osc) - for patch -> python script communication
* [DDSP](https://github.com/magenta/ddsp) (Timbre Transfer Demo Notebook) - The original notebook can be changed, and requires changes for this too.

## Usage

1. The M4L device sends OSC messages to the Python script with settings and audio files.
2. Files are uploaded to Google Drive.
3. The Colab notebook processes the files.
4. Processed audio is sent back to the M4L device.

[Video demonstration](https://player.vimeo.com/video/429263185)


## Notes

- Only works with WAV files in non-temporary folders.
- Keep your Google Drive API key private.
- Google Colab sessions may timeout; restart if necessary.

## Contributing

Feel free to extend the project. Some ideas:
- Windows support
- Display spectral images from the notebook
- Improve Ableton Live integration
- Bug fixes and optimizations

## License

[Specify your license here]
