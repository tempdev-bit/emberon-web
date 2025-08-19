# Emberon Decoder Website

A modern, minimalistic web application for decoding files from Emberon-encoded PNG images.

## Features

- **Drag & Drop Interface**: Simply drag your Emberon PNG files onto the upload area
- **Real-time Progress**: Visual progress bar with status updates during decoding
- **File Information Display**: Shows original filename, file size, compression method, and SHA-256 hash
- **Multiple Compression Support**: Supports zlib and LZMA decompression (ZSTD support planned)
- **Integrity Verification**: Validates file integrity using SHA-256 checksums
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Client-side Processing**: All decoding happens in your browser - no server uploads

## Supported Formats

- **Input**: PNG files encoded with Emberon v2.5+
- **Compression Methods**: 
  - None (uncompressed)
  - Zlib ✅
  - LZMA ✅
  - ZSTD ⏳ (coming soon)

## How to Use

1. **Open the website** in your web browser
2. **Upload your file** by either:
   - Dragging and dropping an Emberon PNG file onto the upload area
   - Clicking the upload area to browse and select a file
3. **Wait for processing** - the progress bar will show decoding status
4. **View file information** - original filename, size, compression details
5. **Download your file** - click the download button to save the decoded file

## Technology Stack

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Libraries**: 
  - [Pako](https://github.com/nodeca/pako) - Zlib decompression
  - [LZMA-JS](https://github.com/LZMA-JS/LZMA-JS) - LZMA decompression
- **Design**: Modern minimalistic UI with smooth animations

## Browser Compatibility

- Chrome/Chromium 80+
- Firefox 75+
- Safari 13+
- Edge 80+

## About Emberon

Emberon is a tool that encodes any file into a lossless PNG image. The encoded PNG contains:

- **Header**: 256-byte header with metadata (filename, compression method, sizes, SHA-256 hash)
- **Payload**: Compressed file data embedded in PNG pixels
- **Magic Bytes**: "EMBERON3" identifier for format validation

## File Structure

```
emberon-web/
├── index.html              # Main HTML file
├── styles.css             # CSS styles
├── emberon-decoder.js     # JavaScript decoder implementation
├── emberon.py            # Original Python Emberon encoder/decoder
└── README.md             # This file
```

## Development

To run locally:

1. Clone this repository
2. Open `index.html` in a web browser
3. Or serve with a local web server:
   ```bash
   python -m http.server 8000
   # Then visit http://localhost:8000
   ```

## Security Features

- **Client-side Processing**: Files never leave your device
- **SHA-256 Verification**: Ensures data integrity
- **Input Validation**: Validates PNG format and Emberon headers
- **Error Handling**: Comprehensive error messages for troubleshooting

## Limitations

- **ZSTD Support**: Not yet implemented (ZSTD was the default compression in Emberon)
- **File Size**: Limited by browser memory for very large files
- **PNG Format**: Only works with RGBA PNG images created by Emberon

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Original Emberon Python implementation for format specification
- Pako library for efficient zlib decompression
- LZMA-JS for LZMA decompression support
