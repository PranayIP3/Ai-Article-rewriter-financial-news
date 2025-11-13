#🪙 Financial News AI Pipeline 🪙

A smart content pipeline that scrapes Indian financial news, filters for quality, and rewrites articles in an engaging, conversational style that actually makes sense to regular readers.

Let's be honest - most financial news sounds like it was written by robots for robots. This pipeline fixes that.

It Scrapes articles from major Indian financial sources (Google News, LiveMint, Moneycontrol), figures out which ones are actually worth reading, and then rewrites them in plain English. Think "explaining to a friend" rather than "corporate press release."

## ⭐ The Problem It Solves

Financial news is everywhere, but most of it is either:
- Dry, jargon-heavy content that puts you to sleep
- Duplicate stories recycled across sites
- Low-quality summaries that don't tell you anything useful

This pipeline handles all three issues automatically.

## ⚙️ How It Works

**Phase 1: Smart Scraping**
- Pulls articles from multiple trusted sources
- Gets full content, not just headlines
- Handles different site structures gracefully

**Phase 2: Quality Filtering**
- Scores each article on multiple factors (length, source credibility, data richness)
- Uses AI to deduplicate and categorize
- Keeps only the best, most unique stories

**Phase 3: Human-Style Rewriting**
- Rewrites in conversational tone
- Explains financial jargon naturally
- Adds context that makes sense to everyday readers
- Maintains all facts and numbers accurately

## Quality Scoring System

Articles are scored on a 100-point scale based on:
- **Content depth** (30 points) - Real substance, not fluff
- **Title quality** (20 points) - Clear and informative
- **Data richness** (15 points) - Contains actual numbers and figures
- **Source credibility** (20 points) - From trusted publications
- **Recency** (15 points) - Fresh, relevant news

Only the top-scoring articles make it through the pipeline.

##🤖 Tech Stack

- **Web Scraping**: BeautifulSoup, newspaper3k
- **AI/LLM**: OpenRouter API (free tier available)
- **Data Processing**: pandas, feedparser
- **Environment**: Designed for Google Colab, runs anywhere

## Setup

1. **Install dependencies:**
```bash
pip install beautifulsoup4 requests pandas newspaper3k lxml[html_clean] openai
```

2. **Get an API key:**
   - Sign up at [OpenRouter](https://openrouter.ai/keys)
   - Plenty for testing and small projects


You'll be prompted for:
- Your OpenRouter API key
- Model selection (Gemini Flash recommended)
- Number of articles per source

## Free Models Available

The pipeline uses OpenRouter's free tier models:
- **Gemini 2.0 Flash** (recommended) - Best for conversational writing
- Mistral 7B Instruct
- Llama 4 Maverick
- MiniMax M2

## Output Files

The pipeline generates two files:

**JSON Format** (`financial_news_[timestamp].json`)
- Structured data with all metadata
- Easy to import into other tools

**Text Format** (`financial_news_[timestamp].txt`)
- Human-readable articles
- Includes quality scores and categories
- Ready to copy/paste or publish



## Customization

**Adjust article volume:**
```python
pipeline.run_pipeline(max_articles_per_source=20)
```

**Change model or temperature:**
```python
ai = AIProcessor(api_key, model="google/gemini-2.0-flash-exp:free")
response = self.call_llm(system_prompt, user_prompt, temperature=0.8)
```

**Modify quality thresholds:**
Edit the `calculate_quality_score()` function to emphasize different factors.

## Limitations

- Requires active internet connection for scraping
- API rate limits apply (built-in delays included)
- Some paywalled content may be inaccessible
- Rewriting quality depends on chosen model

## Use Cases

- Content creators who need fresh perspectives on financial news
- Bloggers looking for engaging financial content
- Researchers aggregating market news
- Anyone tired of reading boring financial articles

## Why I Built This

I got tired of sifting through dozens of nearly-identical financial news articles that all sounded the same. I wanted something that could automatically find the good stuff and make it readable without losing the important details.

This pipeline does exactly that - and it works pretty well.

## Contributing

Found a bug? Have ideas for improvement? Feel free to open an issue or submit a pull request. Always happy to make this better.

## License

MIT License - Use it however you want, just don't blame me if something breaks.

---

**Note**: This is a portfolio project demonstrating web scraping, NLP, and AI integration. The rewritten content should be reviewed before publication.
