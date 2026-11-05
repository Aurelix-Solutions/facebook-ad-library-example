<!-- PUBLISH AFTER: facebook-ad-library is public on the Apify Store -->
# Facebook Ad Library Scraper: Python example

**The problem:** You want to see the ads your competitors run on Facebook and Instagram in a spreadsheet, and know when new ones appear.

**The tool:** [Facebook Ad Library Scraper](https://apify.com/aurelix/facebook-ad-library-scraper), an Apify Actor by Aurelix. This repository is a small, runnable Python example for it.

**The price:** $0.70 per 1,000 ads on Apify's free plan and $0.60 on paid plans, plus $0.003 per run; you pay only for results. Apify's free plan includes $5 of credit a month.

**Try it** (needs an Apify API token from Console > Settings > API & Integrations):

```bash
pip install -r requirements.txt
export APIFY_TOKEN=your_token_here
python main.py
```

[![Facebook Ad Library Scraper: 75-second demo video](https://api.apify.com/v2/key-value-stores/twkCCtTWzsi8fVbx5/records/facebook-ad-library-scraper-demo-thumb-v1.png)](https://api.apify.com/v2/key-value-stores/twkCCtTWzsi8fVbx5/records/facebook-ad-library-scraper-demo-v1.mp4)

**[▶ Watch the 75-second demo](https://api.apify.com/v2/key-value-stores/twkCCtTWzsi8fVbx5/records/facebook-ad-library-scraper-demo-v1.mp4)**

## What it does

Facebook Ad Library Scraper turns ads in the public Meta Ad Library into clean rows: advertiser page, ad text, headline, landing page, button, image and video links, carousel cards, start and stop dates, platforms and active status. Search by keyword, Facebook page ID or an Ad Library URL copied from your browser, and filter by country, active status and media type. Political and issue ads and ads from personal pages are dropped before you pay, and the per-query limit is exact.

## Why this over alternatives

Compared with the leading alternatives on the Apify Store (full table on the Store page):

- $0.70 per 1,000 ads vs $5.80 for Apify's own Facebook Ads Scraper and $0.75 for the most-used community scraper.
- Exact limits (ask for 100, pay for at most 100), plain keywords as input, and an only-new-ads mode with a Slack/webhook digest that neither offers.
- No reliability claim: both alternatives are above 99% run success.

## When to use it

- Marketers and agencies studying competitors' ad copy and creatives
- E-commerce brands tracking which products rivals advertise, with the new-ads feed
- Copywriters collecting ad examples by keyword and country
- Sales teams finding businesses that are actively advertising

## Input example

This is the `skincare-facebook-ads-us` input used in `main.py`:

```json
{
  "queries": [
    "skincare"
  ],
  "country": "US",
  "activeStatus": "active",
  "mediaType": "all",
  "maxResultsPerQuery": 100
}
```

Every input field is documented on the [Store page](https://apify.com/aurelix/facebook-ad-library-scraper).

## How to run

1. Get an Apify API token from Apify Console (Settings, API & Integrations).
2. Install and run:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
export APIFY_TOKEN=your_token_here
python main.py
```

The script starts a run of `aurelix/facebook-ad-library-scraper`, prints a few fields from the first results and writes every result to `results.csv`. Lists and nested objects are stored in the CSV as JSON text. Each run is billed to your Apify account (see Pricing below).

## Sample output

One record as returned by a real run (long text is shortened):

```json
{
  "ad_id": "4477357355914906",
  "page_id": "1811034678977534",
  "page_name": "Coohom",
  "page_url": "https://facebook.com/coohom",
  "page_categories": [
    "Business"
  ],
  "page_like_count": 39638,
  "is_active": true,
  "start_date": "2026-08-26T07:00:00Z",
  "end_date": "2026-11-04T08:00:00Z",
  "platforms": [
    "facebook",
    "instagram",
    "audience_network"
  ],
  "search_country": "ALL",
  "reached_countries": [],
  "ad_text": "From design to production, all in one connected workflow.\n\n✔ Design & render faster\n✔ Quote accurately in real time\n✔ Generate CAM-ready production data\n✔ Connect seamlessly with ERP & API systems\n\nReduce manual work and move from design to production with confidence.\n\nBook a demo and see how Coohom... [50 more characters]",
  "title": "AI-Powered Design to Production",
  "link_description": "Create designs and renders in minutes.",
  "caption": "fb.me",
  "cta_text": "Get quote",
  "cta_type": "GET_QUOTE",
  "link_url": "http://fb.me/",
  "display_format": "DCO",
  "image_urls": [
    "https://scontent-phl2-1.xx.fbcdn.net/v/t39.35426-6/775280732_2238348630340852_5154949849446191823_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=c53f8f&_nc_ohc=tAi5np9bX30Q7kNvwFW8tp7&_nc_oc=AdrJmrE65jt7C0gwdk0Qg2tLV8NCwiMtyyqtwLTiiTiMc0kOYW0ER4VM6Xde4m60wklh8HFTvRBW6m0MDS7cDULN&_nc_zt=14&_nc_ht=scontent-phl2-1.... [111 more characters]",
    "https://scontent-phl2-1.xx.fbcdn.net/v/t39.35426-6/778735461_1427873105866349_7149590165820850646_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=c53f8f&_nc_ohc=cM74U5KQ55oQ7kNvwGMh5eG&_nc_oc=Adov4HCBiq_Dh2lAsA9R1j_JFQw1Oh_zcXQElR-1GkcDqh8D1rXbzzrLRGqjbWwOHvHdgW9Fpx7k1FK2CbhvJOsK&_nc_zt=14&_nc_ht=scontent-phl2-1.... [111 more characters]",
    "https://scontent-phl2-1.xx.fbcdn.net/v/t39.35426-6/779357208_1579852603619327_4038369567686651060_n.jpg?_nc_cat=105&ccb=1-7&_nc_sid=c53f8f&_nc_ohc=mKT2GotyqboQ7kNvwHQkoUF&_nc_oc=AdpSG-hDgtkShLTzg4fJ0A-uWr1ZERIBpAnY8tE1O4smmYumxD0GGcVqP7W8xcq9TUrqwv6Z7Yu4INBKXj5uhl27&_nc_zt=14&_nc_ht=scontent-phl2-1.... [111 more characters]",
    "https://scontent-phl2-1.xx.fbcdn.net/v/t39.35426-6/775442161_1589960839142348_3054016414017708668_n.jpg?_nc_cat=107&ccb=1-7&_nc_sid=c53f8f&_nc_ohc=qqk4yUxAcrQQ7kNvwEV3Rqn&_nc_oc=Adp8uxJBRR3sZGYkDw7c_x07XBiHxcwRklH2wylZWD6ekF0YSiePfues0BoG8rtA4luCQTq5eVwiKXWPgp8CtVJE&_nc_zt=14&_nc_ht=scontent-phl2-1.... [111 more characters]",
    "https://scontent-phl2-1.xx.fbcdn.net/v/t39.35426-6/777297769_2211000859681052_7107529719016081252_n.jpg?_nc_cat=105&ccb=1-7&_nc_sid=c53f8f&_nc_ohc=w4Yns0uyFrwQ7kNvwHZLfqF&_nc_oc=AdqylakuCn1wcJkVivrS3yzpb43sa6l3Sgdd8zm6FRAIHtF5ppxCPSoRAcOSeRfdKeXo4JLJ8HR-pXRaLuCbfvil&_nc_zt=14&_nc_ht=scontent-phl2-1.... [111 more characters]",
    "... [7 more]"
  ],
  "video_urls": [
    "https://video-phl2-1.xx.fbcdn.net/o1/v/t2/f2/m412/AQNWAem6W_OqTU0qvfnndgBECIVlL_Co5FiUTxZVrq9uU7fm_5dZlE9waeqy8weHO2Y_YK7Z46Sr44snspwq6mr9kLCW8qiOIknHpeVSLA.mp4?_nc_cat=104&_nc_sid=ef5aa3&_nc_ht=video-phl2-1.xx.fbcdn.net&_nc_ohc=vtarHx0SMUIQ7kNvwGTCOh6&efg=eyJ2ZW5jb2RlX3RhZyI6Inhwdl9wcm9ncmVzc2l2ZS5... [329 more characters]"
  ],
  "cards": [
    {
      "body": "From design to production, all in one connected workflow.\n\n✔ Design & render faster\n✔ Quote accurately in real time\n✔ Generate CAM-ready production data\n✔ Connect seamlessly with ERP & API systems\n\nReduce manual work and move from design to production with confidence.\n\nBook a demo and see how Coohom... [50 more characters]",
      "title": "AI-Powered Design to Production",
      "link_url": "http://fb.me/",
      "image_url": "https://scontent-phl2-1.xx.fbcdn.net/v/t39.35426-6/775280732_2238348630340852_5154949849446191823_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=c53f8f&_nc_ohc=tAi5np9bX30Q7kNvwFW8tp7&_nc_oc=AdrJmrE65jt7C0gwdk0Qg2tLV8NCwiMtyyqtwLTiiTiMc0kOYW0ER4VM6Xde4m60wklh8HFTvRBW6m0MDS7cDULN&_nc_zt=14&_nc_ht=scontent-phl2-1.... [111 more characters]",
      "video_url": null
    },
    {
      "body": "From design to production, all in one connected workflow.\n\n✔ Design & render faster\n✔ Quote accurately in real time\n✔ Generate CAM-ready production data\n✔ Connect seamlessly with ERP & API systems\n\nReduce manual work and move from design to production with confidence.\n\nBook a demo and see how Coohom... [50 more characters]",
      "title": "Design Faster. Sell Smarter.",
      "link_url": "http://fb.me/",
      "image_url": "https://scontent-phl2-1.xx.fbcdn.net/v/t39.35426-6/778735461_1427873105866349_7149590165820850646_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=c53f8f&_nc_ohc=cM74U5KQ55oQ7kNvwGMh5eG&_nc_oc=Adov4HCBiq_Dh2lAsA9R1j_JFQw1Oh_zcXQElR-1GkcDqh8D1rXbzzrLRGqjbWwOHvHdgW9Fpx7k1FK2CbhvJOsK&_nc_zt=14&_nc_ht=scontent-phl2-1.... [111 more characters]",
      "video_url": null
    },
    {
      "body": "From design to production, all in one connected workflow.\n\n✔ Design & render faster\n✔ Quote accurately in real time\n✔ Generate CAM-ready production data\n✔ Connect seamlessly with ERP & API systems\n\nReduce manual work and move from design to production with confidence.\n\nBook a demo and see how Coohom... [50 more characters]",
      "title": "AI-Powered Design to Production",
      "link_url": "http://fb.me/",
      "image_url": "https://scontent-phl2-1.xx.fbcdn.net/v/t39.35426-6/779357208_1579852603619327_4038369567686651060_n.jpg?_nc_cat=105&ccb=1-7&_nc_sid=c53f8f&_nc_ohc=mKT2GotyqboQ7kNvwHQkoUF&_nc_oc=AdpSG-hDgtkShLTzg4fJ0A-uWr1ZERIBpAnY8tE1O4smmYumxD0GGcVqP7W8xcq9TUrqwv6Z7Yu4INBKXj5uhl27&_nc_zt=14&_nc_ht=scontent-phl2-1.... [111 more characters]",
      "video_url": null
    },
    {
      "body": "From design to production, all in one connected workflow.\n\n✔ Design & render faster\n✔ Quote accurately in real time\n✔ Generate CAM-ready production data\n✔ Connect seamlessly with ERP & API systems\n\nReduce manual work and move from design to production with confidence.\n\nBook a demo and see how Coohom... [50 more characters]",
      "title": "Design Faster. Sell Smarter.",
      "link_url": "http://fb.me/",
      "image_url": "https://scontent-phl2-1.xx.fbcdn.net/v/t39.35426-6/775442161_1589960839142348_3054016414017708668_n.jpg?_nc_cat=107&ccb=1-7&_nc_sid=c53f8f&_nc_ohc=qqk4yUxAcrQQ7kNvwEV3Rqn&_nc_oc=Adp8uxJBRR3sZGYkDw7c_x07XBiHxcwRklH2wylZWD6ekF0YSiePfues0BoG8rtA4luCQTq5eVwiKXWPgp8CtVJE&_nc_zt=14&_nc_ht=scontent-phl2-1.... [111 more characters]",
      "video_url": null
    },
    {
      "body": "From design to production, all in one connected workflow.\n\n✔ Design & render faster\n✔ Quote accurately in real time\n✔ Generate CAM-ready production data\n✔ Connect seamlessly with ERP & API systems\n\nReduce manual work and move from design to production with confidence.\n\nBook a demo and see how Coohom... [50 more characters]",
      "title": "AI-Powered Design to Production",
      "link_url": "http://fb.me/",
      "image_url": "https://scontent-phl2-1.xx.fbcdn.net/v/t39.35426-6/777297769_2211000859681052_7107529719016081252_n.jpg?_nc_cat=105&ccb=1-7&_nc_sid=c53f8f&_nc_ohc=w4Yns0uyFrwQ7kNvwHZLfqF&_nc_oc=AdqylakuCn1wcJkVivrS3yzpb43sa6l3Sgdd8zm6FRAIHtF5ppxCPSoRAcOSeRfdKeXo4JLJ8HR-pXRaLuCbfvil&_nc_zt=14&_nc_ht=scontent-phl2-1.... [111 more characters]",
      "video_url": null
    },
    "... [13 more]"
  ],
  "variants_count": 1,
  "collation_id": "1087839470334171",
  "spend_range": null,
  "impressions_range": null,
  "impressions_text": null,
  "reach_estimate": null,
  "currency": null,
  "ad_library_url": "https://www.facebook.com/ads/library/?id=4477357355914906",
  "source_url": "https://www.facebook.com/ads/library/?id=4477357355914906",
  "scraped_at": "2026-11-04T16:15:38Z"
}
```

## Export to CSV

`main.py` writes `results.csv` with the `csv` module. You can also download any run's results directly:

```
https://api.apify.com/v2/datasets/<datasetId>/items?format=csv&clean=true
```

Send your token in an `Authorization: Bearer <token>` header (or `?token=`) if the dataset is not readable without one. Other formats: `format=json`, `format=xlsx`.

## Google Sheets

- Simplest: use Apify's Google Sheets integration on the Actor or a saved task, so each run's results land in a sheet with no token in the sheet itself.
- Quick pull of one run: `=IMPORTDATA("https://api.apify.com/v2/datasets/<datasetId>/items?format=csv&clean=true")`. This only works without a token if your account lets anyone with the dataset ID read it. Do not paste an API token into a sheet formula: anyone who can view or copy the sheet can read it and use your account.

## n8n

- Apify node: choose "Run an Actor", enter `aurelix/facebook-ad-library-scraper`, paste the input above, then read the run's dataset items.
- HTTP Request node: `POST https://api.apify.com/v2/acts/aurelix~facebook-ad-library-scraper/run-sync-get-dataset-items` with header `Authorization: Bearer <token>` (stored as an n8n credential) and the input as the JSON body. The response is the list of results. This endpoint waits for the run to finish, so for large runs start the run asynchronously and fetch the dataset when it ends.

## Limits

- Data comes from the public Ad Library web pages, not Meta's official API (which needs a personally verified developer account). A Meta layout change can break it until fixed; the daily health run catches that within 24 hours.
- Facebook blocks many datacenter addresses, so reliable runs need residential proxies, which are included in the price.
- The personal-page filter is a heuristic on Meta's page categories and page names. A person with an unusual name who files their page under a business category can slip through; a business with no category, or one named exactly like a person (e.g. 'Sarah Jane'), is dropped.
- Meta groups near-identical ad versions; each version is returned as its own row with 'variants_count'.
- Reached-countries, spend and impressions are only filled where Meta publishes them (mostly EU and political ads).
- Meta rate-limits the Ad Library from time to time. The Actor waits and retries with up to 8 fresh residential sessions (new IP addresses), backing off up to a minute between tries. If Meta still refuses, that query stops early: the run still succeeds, its status message says PARTIAL and names the query, and you pay only for the ads returned.
- A run that would outlast its timeout stops by itself shortly before it, keeps and charges only the ads already saved, and ends SUCCEEDED with a PARTIAL status message. With the default 1-hour timeout that is several thousand ads; raise the timeout for bigger pulls.

## Pricing

At the time of writing:

Pay per event: you pay only for what the run returns, plus a small start fee. Bronze, Silver, Gold and higher Apify plans pay less per result.

| Event | Free plan | Paid plans (Bronze, Silver, Gold) |
|---|---|---|
| `ad-result` | $0.70 per 1,000 ads | $0.60 per 1,000 ads |
| `eu-details` | $0.20 per 1,000 ads with EU data | $0.20 per 1,000 ads with EU data |
| `apify-actor-start` | $0.003 per run | $0.003 per run |

Example: 1,000 ads cost $0.70 on the free plan and $0.60 on a paid plan, plus the start fee. Apify's free plan includes $5 of credit a month, enough for about 7,100 ads.

Proxy cost (datacenter first, residential when Meta rate-limits) is included. Paid Apify plans pay $0.60 per 1,000 ads. EU transparency data is optional and costs $0.20 per 1,000 ads that get it; ads without EU data are not charged for it. Excluded political and personal-page ads and duplicates are never charged.

Check the [Store page](https://apify.com/aurelix/facebook-ad-library-scraper) for current prices.

## Links

- Actor: https://apify.com/aurelix/facebook-ad-library-scraper
- Questions, bugs and feature requests: the Issues tab on the Store page.

## Licence

The example code in this repository is released under the MIT licence (see `LICENSE`). The Actor itself runs on Apify and is billed through your Apify account.
