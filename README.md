# matn_pala_gold_1.2.7
# MatnPala - AI-Powered Text Summarizer with Tone Detection

MatnPala is a lightweight, high-performance text summarization engine for Persian (Farsi) and English. It uses a multi-factor scoring system with tone detection, statistics preservation, and adjustable compression — all in a single PHP file, with no dependencies.

## Features

- Tone Detection — Formal, Scientific, News, Literary, Legal, Informal
- Statistics Preservation — Keeps numbers, percentages, dates intact
- Adjustable Compression — 20% (detailed) to 80% (very short)
- Enhanced Generation Mode — Auto-generates intro and conclusion
- Bilingual — Persian and English with auto language detection
- Negative Sentence Preservation — Important negative statements boosted
- Original Sentence Order — Selected sentences retain original flow
- 40+ Text Templates — Analysis, report, study, review, and more
- Built-in Security — CSRF, Rate Limiting, XSS, SQL Injection protection, AES-256
- Single File — Pure PHP 8.0+, no frameworks, no external libraries
- Ultra-fast — Processes up to 50,000 characters in under 2 seconds

## Quick Start

```bash
git clone https://github.com/yourusername/matnpala.git
cd matnpala
```

Upload to your PHP server. Requirements: PHP 8.0+, mbstring, openssl. No installation needed.

## API Usage

```bash
curl -X POST https://matnpala.ir/ \
  -F "text=Your long text here" \
  -F "ratio=0.5" \
  -F "generate=1" \
  -F "csrf_token=YOUR_TOKEN"
```

### Parameters

| Parameter | Type | Description | Default |
|-----------|------|-------------|---------|
| text | string | Input text (5–50,000 chars) | Required |
| ratio | float | Compression ratio (0.20–0.80) | 0.5 |
| generate | bool | Enable intro/conclusion | 0 |
| csrf_token | string | CSRF token from cookie | Required |

### Response

```json
{
  "success": true,
  "summary": "Summarized text here...",
  "stats": {
    "original_length": 1721,
    "summary_length": 177,
    "compression_ratio": 89.7,
    "target_compression": 50.0,
    "total_sentences": 13,
    "sentences_extracted": 3,
    "processing_time": 0.143,
    "language": "en"
  }
}
```

## How It Works

MatnPala uses a multi-factor scoring algorithm:

1. TF-IDF Scoring
2. Position Weighting
3. Length Optimization
4. Negative Sentence Boost (1.5x)
5. Positive Sentence Boost (1.15x)
6. Statistics Boost (1.35x)
7. Keyword Boost (1.25x)
8. MMR Diversity
9. Tone Awareness
10. Language Detection

## Security

- CSRF Protection
- Rate Limiting (30 req/60s)
- IP Blocking
- XSS Protection
- SQL Injection Detection
- AES-256-CBC Encryption
- CSP Headers with nonce
- HSTS

## License

MIT License

## Contact

- Website: https://matnpala.ir
- Email: info@matnpala.ir
- Developer: Mohammad Taha Mokhtarian

Built with love for Persian and English speakers worldwide.
