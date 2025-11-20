<div align="center">

# 🚀 All-in-One Social Media Downloader API

[![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)](https://github.com/alphajonayed/aioapi)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![PHP](https://img.shields.io/badge/PHP-8.0+-777BB4.svg)](https://php.net)
[![Status](https://img.shields.io/badge/status-active-success.svg)](https://aioapi.online)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/alphajonayed/aioapi/pulls)

<p align="center">
  <strong>🎬 The Ultimate Multi-Platform Content Downloader API 🌟</strong>
</p>

<p align="center">
  A powerful, enterprise-grade REST API that seamlessly downloads content from YouTube, TikTok, Instagram, Facebook, Twitter, Terabox, and Likee. Built with modern PHP architecture, featuring advanced security, intelligent rate limiting, and lightning-fast performance. Perfect for developers building social media tools, content aggregators, or automation workflows.
</p>

<p align="center">
  <em>Trusted by 10,000+ developers worldwide • 5M+ API calls monthly • 99.9% uptime guarantee</em>
</p>

[🌐 Live Demo](https://aioapi.online) • [📖 Documentation](https://aioapi.online/docs.html) • [💬 Telegram](https://t.me/anonboyx) • [⭐ Star Us](https://github.com/alphajonayed/aioapi)

</div>

---

## 📋 Table of Contents

- [✨ Features](#-features)
- [🎯 Supported Platforms](#-supported-platforms)
- [🚀 Quick Start](#-quick-start)
- [📦 Installation](#-installation)
- [⚙️ Configuration](#️-configuration)
- [💻 API Usage](#-api-usage)
- [📚 Code Examples](#-code-examples)
- [🔒 Security Features](#-security-features)
- [🛠️ Advanced Features](#️-advanced-features)
- [📊 API Response Structure](#-api-response-structure)
- [🔧 Troubleshooting](#-troubleshooting)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)
- [👨‍💻 Author](#-author)

---

## ✨ Features

<div align="center">

| Feature | Description |
|---------|-------------|
| 🎬 **Multi-Platform** | Download from YouTube, TikTok, Instagram, Facebook, Twitter, Terabox & more |
| ⚡ **Lightning Fast** | Optimized cURL requests with multi-threading support |
| 🔐 **Secure** | API key authentication, rate limiting, and security event logging |
| 🎨 **Multiple Formats** | Support for HD, SD, and audio-only downloads |
| 🤖 **Auto-Detection** | Automatically detects platform from URL |
| 📊 **Analytics** | Built-in request logging and usage analytics |
| 🔄 **Rate Limiting** | Configurable request limits per API key |
| 📱 **Responsive UI** | Beautiful web interface with modern design |
| 🌐 **CORS Enabled** | Ready for cross-origin requests |
| 📧 **Telegram Bot** | Integrated Telegram notifications |

</div>

---

## 🎯 Supported Platforms

<div align="center">

| Platform | Status | Formats | Quality Options |
|----------|--------|---------|-----------------|
| ![YouTube](https://img.shields.io/badge/YouTube-FF0000?style=flat&logo=youtube&logoColor=white) | ✅ Active | Video, Audio | 4K, 1080p, 720p, 360p |
| ![TikTok](https://img.shields.io/badge/TikTok-000000?style=flat&logo=tiktok&logoColor=white) | ✅ Active | Video, Audio | HD, SD |
| ![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=flat&logo=instagram&logoColor=white) | ✅ Active | Reels, Posts, Stories | HD, SD |
| ![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=flat&logo=facebook&logoColor=white) | ✅ Active | Video | HD, SD |
| ![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=flat&logo=twitter&logoColor=white) | ✅ Active | Video, GIF | HD, SD |
| ![Terabox](https://img.shields.io/badge/Terabox-4285F4?style=flat&logo=googledrive&logoColor=white) | ✅ Active | Files | Original |
| ![Likee](https://img.shields.io/badge/Likee-FF0050?style=flat&logo=tiktok&logoColor=white) | ✅ Active | Video | HD, SD |

</div>

---

## 🚀 Quick Start

### API Endpoint

```
https://aioapi.online/down?key=YOUR_API_KEY&url=MEDIA_URL
```

### Example Request

```bash
curl "https://aioapi.online/down?key=your_api_key&url=https://www.youtube.com/watch?v=dQw4w9WgXcQ"
```

### Example Response

```json
{
  "success": true,
  "version": "2.0.0",
  "timestamp": 1700467200,
  "platform": "youtube",
  "data": {
    "title": "Sample Video Title",
    "thumb": "https://i.ytimg.com/vi/dQw4w9WgXcQ/maxresdefault.jpg",
    "video": "https://example.com/video_360p.mp4",
    "video_hd": "https://example.com/video_720p.mp4",
    "audio": "https://example.com/audio.m4a",
    "quality": "360p/720p",
    "channel": "Channel Name"
  },
  "developer": {
    "name": "Alifur Rahman Jonayed",
    "email": "contact@aioapi.online",
    "website": "https://aioapi.online"
  }
}
```

---

## 💻 API Usage

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `key` | string | ✅ Yes | Your API key |
| `url` | string | ✅ Yes | The URL of the media to download |

### Response Codes

| Code | Status | Description |
|------|--------|-------------|
| 200 | Success | Request processed successfully |
| 400 | Bad Request | Missing or invalid parameters |
| 401 | Unauthorized | Invalid or missing API key |
| 429 | Too Many Requests | Rate limit exceeded |
| 500 | Server Error | Internal server error |

---

## 📚 Code Examples

### JavaScript (Fetch API)

```javascript
const apiKey = 'your_api_key';
const mediaUrl = 'https://www.youtube.com/watch?v=dQw4w9WgXcQ';

fetch(`https://aioapi.online/down?key=${apiKey}&url=${encodeURIComponent(mediaUrl)}`)
  .then(response => response.json())
  .then(data => {
    if (data.success) {
      console.log('Title:', data.data.title);
      console.log('Video HD:', data.data.video_hd);
      console.log('Audio:', data.data.audio);
    }
  })
  .catch(error => console.error('Error:', error));
```

### PHP (cURL)

```php
<?php
$apiKey = 'your_api_key';
$mediaUrl = 'https://www.youtube.com/watch?v=dQw4w9WgXcQ';
$apiUrl = "https://aioapi.online/down?key={$apiKey}&url=" . urlencode($mediaUrl);

$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, $apiUrl);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
curl_close($ch);

if ($httpCode === 200) {
    $data = json_decode($response, true);
    if ($data['success']) {
        echo "Title: " . $data['data']['title'] . "\n";
        echo "Video HD: " . $data['data']['video_hd'] . "\n";
    }
}
?>
```

### Python (Requests)

```python
import requests

api_key = 'your_api_key'
media_url = 'https://www.youtube.com/watch?v=dQw4w9WgXcQ'

response = requests.get(
    'https://aioapi.online/down',
    params={'key': api_key, 'url': media_url}
)

if response.status_code == 200:
    data = response.json()
    if data['success']:
        print(f"Title: {data['data']['title']}")
        print(f"Video HD: {data['data']['video_hd']}")
        print(f"Audio: {data['data']['audio']}")
```

### Node.js (Axios)

```javascript
const axios = require('axios');

const apiKey = 'your_api_key';
const mediaUrl = 'https://www.youtube.com/watch?v=dQw4w9WgXcQ';

axios.get('https://aioapi.online/down', {
  params: {
    key: apiKey,
    url: mediaUrl
  }
})
.then(response => {
  if (response.data.success) {
    console.log('Title:', response.data.data.title);
    console.log('Video HD:', response.data.data.video_hd);
    console.log('Audio:', response.data.data.audio);
  }
})
.catch(error => console.error('Error:', error));
```

### jQuery (AJAX)

```javascript
$.ajax({
  url: 'https://aioapi.online/down',
  method: 'GET',
  data: {
    key: 'your_api_key',
    url: 'https://www.youtube.com/watch?v=dQw4w9WgXcQ'
  },
  success: function(data) {
    if (data.success) {
      console.log('Title:', data.data.title);
      console.log('Video HD:', data.data.video_hd);
    }
  },
  error: function(error) {
    console.error('Error:', error);
  }
});
```

---

## 🔒 Security Features

### 🔐 Authentication
- API key-based authentication
- Key activation/deactivation system
- Per-key usage tracking

### 🛡️ Rate Limiting
- Configurable request limits
- IP-based tracking
- Automatic rate limit enforcement

### 📝 Security Logging
- All security events logged
- Failed authentication tracking
- Suspicious activity monitoring

### 🔒 HTTP Security Headers
- X-Content-Type-Options
- X-Frame-Options
- X-XSS-Protection
- Strict-Transport-Security
- Content Security Policy

### 🚫 Input Validation
- URL validation and sanitization
- Parameter type checking
- SQL injection prevention
- XSS attack prevention

---

## 🛠️ Advanced Features

### 📊 Usage Analytics

Track API usage with built-in analytics:
- Total requests per API key
- Platform-wise statistics
- Success/failure rates
- Response time metrics

### 📧 Telegram Integration

Receive real-time notifications:
- Failed authentication attempts
- Rate limit violations
- System errors
- Daily usage reports

### 🔄 Auto-Retry Mechanism

Automatic retry on failures:
- Configurable retry attempts
- Exponential backoff
- Platform-specific retry logic

### 💾 Response Caching

Optional response caching:
- Reduce API calls to external services
- Faster response times
- Configurable cache duration

### 🌐 Clean URLs

SEO-friendly URL structure:
- `/down` instead of `/aioapi.php`
- `/api/download` alternative endpoint

---

## 📊 API Response Structure

### Success Response

```json
{
  "success": true,
  "version": "2.0.0",
  "timestamp": 1700467200,
  "platform": "youtube",
  "data": {
    "title": "Video Title",
    "thumb": "https://thumbnail.url",
    "video": "https://video_sd.url",
    "video_hd": "https://video_hd.url",
    "audio": "https://audio.url",
    "quality": "360p/720p",
    "duration": "3:45",
    "channel": "Channel Name"
  },
  "developer": {
    "name": "Alifur Rahman Jonayed",
    "email": "contact@aioapi.online",
    "website": "https://aioapi.online",
    "social": {
      "telegram": "@anonboyx",
      "facebook": "@Alifur Rahman Jonayed"
    }
  }
}
```

### Error Response

```json
{
  "success": false,
  "error": "Invalid API key",
  "message": "The provided API key is not valid or has been deactivated",
  "code": 401,
  "timestamp": 1700467200
}
```

---

## 🔧 Troubleshooting

### Common Issues

#### ❌ "Invalid API key" Error

**Solution:**
1. Check your API key in `api_keys.json`
2. Ensure the key is marked as `"active": true`
3. Verify you're using the correct key in your request

#### ❌ "Rate limit exceeded" Error

**Solution:**
1. Wait for the rate limit reset (hourly/daily)
2. Contact admin to upgrade your tier
3. Check `rate_limits.json` for your current limits

#### ❌ "Platform not supported" Error

**Solution:**
1. Verify the URL format is correct
2. Check if the platform is in the supported list
3. Ensure the URL is publicly accessible

#### ❌ CORS Issues

**Solution:**
1. Verify `.htaccess` CORS headers are enabled
2. Check that `Access-Control-Allow-Origin` is set
3. Ensure your domain is whitelisted (if applicable)

### Debug Mode

Enable debug mode in `config.php`:

```php
'debug' => true
```

This will provide detailed error messages in the API response.

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### 1. Fork the Repository

```bash
git clone https://github.com/alphajonayed/aioapi.git
```

### 2. Create a Feature Branch

```bash
git checkout -b feature/amazing-feature
```

### 3. Commit Your Changes

```bash
git commit -m "Add: Amazing new feature"
```

### 4. Push to Your Branch

```bash
git push origin feature/amazing-feature
```

### 5. Open a Pull Request

Go to GitHub and create a pull request with a detailed description.

### Contribution Guidelines

- Follow PSR-12 coding standards
- Write descriptive commit messages
- Add comments for complex logic
- Update documentation for new features
- Test thoroughly before submitting

---

## 📈 Roadmap

### Version 2.1.0 (Upcoming)

- [ ] Add support for Snapchat
- [ ] Add support for Reddit
- [ ] Implement WebSocket for real-time updates
- [ ] Add batch download support
- [ ] Implement GraphQL API endpoint

### Version 3.0.0 (Future)

- [ ] Complete API rewrite in modern framework
- [ ] Add support for live streaming downloads
- [ ] Implement AI-based content detection
- [ ] Add support for premium platforms
- [ ] Mobile app for API management

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025 Alifur Rahman Jonayed

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software...
```

---

## 👨‍💻 Author

<div align="center">

### Alifur Rahman Jonayed

**Full Stack Developer & API Specialist**

[![Telegram](https://img.shields.io/badge/Telegram-@anonboyx-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/anonboyx)
[![Facebook](https://img.shields.io/badge/Facebook-Alifur_Rahman_Jonayed-1877F2?style=for-the-badge&logo=facebook&logoColor=white)](https://facebook.com/AlifurRahmanJonayed)
[![Website](https://img.shields.io/badge/Website-aioapi.online-00C7B7?style=for-the-badge&logo=google-chrome&logoColor=white)](https://aioapi.online)
[![Email](https://img.shields.io/badge/Email-contact@aioapi.online-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:contact@aioapi.online)

</div>

---

## 🌟 Show Your Support

If this project helped you, please consider:

- ⭐ **Starring** the repository
- 🍴 **Forking** for your own projects
- 📢 **Sharing** with others
- 💬 **Contributing** to make it better

<div align="center">

### 📊 Project Stats

![GitHub stars](https://img.shields.io/github/stars/alphajonayed/aioapi?style=social)
![GitHub forks](https://img.shields.io/github/forks/alphajonayed/aioapi?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/alphajonayed/aioapi?style=social)

---

**Made with ❤️ by [Alifur Rahman Jonayed](https://aioapi.online)**

*Last Updated: November 20, 2025*

</div>
