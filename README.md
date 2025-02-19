# GitHub Achievements API

[![License](https://img.shields.io/github/license/wangrunlin/github-achievements-api)](https://github.com/wangrunlin/github-achievements-api/blob/main/LICENSE)
[![GitHub package.json version](https://img.shields.io/github/package-json/v/wangrunlin/github-achievements-api)](https://github.com/wangrunlin/github-achievements-api/blob/main/package.json)
[![GitHub last commit](https://img.shields.io/github/last-commit/wangrunlin/github-achievements-api)](https://github.com/wangrunlin/github-achievements-api/commits)
[![Test Status](https://img.shields.io/github/actions/workflow/status/wangrunlin/github-achievements-api/test.yml?label=test)](https://github.com/wangrunlin/github-achievements-api/actions)

English | [简体中文](README_zh.md)

A simple API service for retrieving GitHub user achievements information. Built with Cloudflare Workers.

## Live Demo

- [https://github-achievements-api.wangrunlin.workers.dev](https://github-achievements-api.wangrunlin.workers.dev)

## Deploy to Cloudflare Workers

[![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/wangrunlin/github-achievements-api)

## Features

- Fetch GitHub user achievement list
- Support for achievement tier statistics
- Provide raw and weighted achievement counts
- Automatic result caching (1 hour) for better performance
- Deployed on Cloudflare Workers for low-latency global access

## API Usage

### Base Endpoint

```http
GET https://<your-worker>.workers.dev/<github_username>
```

### Example Request

```http
GET https://<your-worker>.workers.dev/wangrunlin
```

### Response Format

```json
{
	"total": {
		"raw": 5, // Raw achievement count (without tiers)
		"weighted": 8 // Weighted achievement count (with tiers)
	},
	"achievements": [
		{
			"type": "pair-extraordinaire",
			"tier": 3
		},
		{
			"type": "pull-shark",
			"tier": 2
		},
		{
			"type": "quickdraw",
			"tier": 1
		}
		// ...
	]
}
```

## Local Development

### Prerequisites

- Node.js 18+
- pnpm

### Install Dependencies

```bash
pnpm install
```

### Run Locally

```bash
pnpm dev
```

### Run Tests

```bash
pnpm test
```

## Deployment

1. Login to Cloudflare

```bash
pnpm dlx wrangler login
```

2. Deploy Worker

```bash
pnpm deploy
```

## Tech Stack

- TypeScript
- Cloudflare Workers
- Vitest (Testing Framework)
- Wrangler (Development & Deployment Tool)

## License

MIT

## Contributing

Issues and Pull Requests are welcome!

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Author

[Leo Wang](https://github.com/wangrunlin)

## Acknowledgments

- GitHub Achievement System
- Cloudflare Workers Platform
