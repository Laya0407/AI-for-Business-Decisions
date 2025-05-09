# Sprint 5: TikTok Influencer Marketing Analysis

## Project Overview
This project provides a comprehensive analysis of TikTok influencers and app reviews to develop optimal influencer marketing strategies. The analysis consists of two main components: 1) Influencer classification and segmentation to identify the most effective partners, and 2) Sentiment analysis of app reviews to understand user perceptions and platform strengths/weaknesses.

## Dataset Description
The analysis utilizes two datasets:
1. **TikTok Profiles Dataset**
   - Influencer account metrics (followers, following, likes)
   - Engagement rates
   - Content volume (videos count)
   - Profile information

2. **TikTok App Reviews Dataset**
   - Review text
   - Rating scores
   - Upvotes
   - App version
   - Posted date

## Part 1: Influencer Classification & Analysis

### Methodology
- **Data Preprocessing**: Cleaned metrics data and handled missing values
- **Exploratory Analysis**: Examined distribution of followers, engagement rates, and content volume
- **Clustering**: Applied K-Means to identify natural influencer groupings
- **Business-Driven Categorization**: Developed a practical classification system based on followers and engagement rates

### Influencer Categories
Created a four-tier classification system:
1. **Ideal Partners** (0.4%): High followers + high engagement
   - Average followers: 843,575
   - Average engagement rate: 40.5%
   - Best for major campaigns but rare and expensive

2. **Niche Influencers** (19.4%): Lower followers + high engagement
   - Average followers: 3,843
   - Average engagement rate: 264.4%
   - Excellent ROI for targeted campaigns

3. **Awareness Drivers** (18.7%): High followers + lower engagement
   - Average followers: 550,701
   - Average engagement rate: 4.1%
   - Good for broad reach campaigns

4. **Emerging Creators** (61.5%): Lower followers + lower engagement
   - Average followers: 9,733
   - Average engagement rate: 6.6%
   - Potential for long-term partnerships

### Key Findings
- Strong inverse relationship between follower count and engagement rate
- Niche influencers offer potentially highest ROI despite smaller audience
- Ideal partners are extremely rare (only 0.4% of the dataset)
- Emerging creators constitute the majority of the platform (61.5%)

## Part 2: App Review Sentiment Analysis

### Methodology
- **Sentiment Scoring**: Utilized VADER (Valence Aware Dictionary for Sentiment Reasoning) for sentiment analysis
- **Temporal Analysis**: Tracked sentiment changes over time (2015-2021)
- **Version Analysis**: Analyzed sentiment across different app versions
- **Content Analysis**: Generated word clouds and key themes from positive and negative reviews

### Sentiment Distribution
- Positive: 79.6%
- Neutral: 15.7%
- Negative: 4.7%

### Key Findings
- **Overall Positive Reception**: The vast majority of reviews (80%) express positive sentiment
- **Temporal Trends**: Positive sentiment remained consistently high (75-85%) throughout 2015-2021
- **Version Impact**: Identified specific app versions with higher negative sentiment (9.1.0, 18.3.6, 10.5.0)
- **Feature Reception**: Technical functionality issues dominate negative feedback while entertainment value drives positive reviews

### Content Themes
- **Positive Keywords**: love, fun, video, amazing, easy, friends, use, tiktok
- **Negative Keywords**: problem, update, account, hate, fix, phone, time, upload
- **Emotional Drivers**: Entertainment value and creative expression are key positives
- **Pain Points**: Technical reliability, feature access, and update-related dissatisfaction

## Business Recommendations

### Influencer Strategy
1. **Focus on Niche Influencers** for highest ROI and engagement
2. **Use Awareness Drivers** for broad campaigns like product launches
3. **Build relationships with Emerging Creators** showing growth potential
4. **Reserve Ideal Partners** for flagship campaigns with major budget

### Platform Insights
1. **Emphasize creative and entertainment value** in marketing messages
2. **Address technical reliability** in platform development
3. **Carefully manage app updates** to minimize negative sentiment spikes
4. **Leverage strong positive sentiment** (80%) in brand positioning

### Implementation Guidance
1. **Tiered Budget Allocation**:
   - 60% to Niche Influencers
   - 30% to selective Awareness Drivers
   - 10% to promising Emerging Creators

2. **Content Strategy Optimization**:
   - Focus on entertainment and creativity aspects
   - Avoid technical complexity that could trigger reliability concerns
   - Emphasize social connection and sharing features

## Technologies Used
- Python (pandas, numpy)
- Machine learning (K-Means clustering)
- Natural language processing (VADER sentiment analysis)
- Data visualization (matplotlib, seaborn, wordcloud)

## Future Work
- Develop more sophisticated engagement metrics beyond basic ratios
- Implement time series forecasting for influencer growth prediction
- Create automated influencer recommendation system
- Incorporate content analysis using computer vision and NLP

## Team Members
- Motolani Akingbade
- Miracle Messiri
- Layanika Vinay Saravanan
