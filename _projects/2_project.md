---
layout: page
title: Adobe Behaviour Simulation Challenge
description: Inter IIT Tech Meet 12.0 - Social Media Content & Behavior Analysis
img: assets/img/social-media-ai.jpg
importance: 2
category: ml
github: https://github.com/himanshu-skid19
giscus_comments: true
---

## Project Overview

Developed a comprehensive system for social media behavior simulation and content generation, leveraging a combination of classic machine learning models, transformers, and large language models to analyze and predict user behavior on Twitter.

## Challenge Description

The Adobe Behaviour Simulation Challenge required building models that could:
- **Predict User Engagement**: Accurately forecast likes, retweets, and other engagement metrics
- **Generate Content**: Create realistic social media content and captions
- **Understand Behavior Patterns**: Analyze and simulate user behavior across different content types

## Technical Architecture

### 1. Tweet Classification & Bucketing
- **DistilBERT Classifier**: Trained a DistilBERT model to categorize tweets into different buckets
- **Multi-class Classification**: Handled various tweet types and content categories
- **Feature Engineering**: Extracted meaningful features from tweet text, metadata, and user information

### 2. Engagement Prediction
- **Bucket-specific Regressors**: Developed separate regression models for each tweet bucket
- **Likes Prediction**: Specialized models to predict engagement metrics
- **Performance Optimization**: Fine-tuned models for accuracy and inference speed

### 3. Media Description & Captioning
- **BLIP-2 Integration**: Used BLIP-2 for automatic image description generation
- **Metadata Fusion**: Combined visual descriptions with tweet metadata
- **Llama-2 Fine-tuning**: Fine-tuned Llama-2 for context-aware captioning

## Results & Performance

### Classification Performance
- **74.3% accuracy** in bucket classification
- **Robust Performance**: Consistent results across different tweet categories
- **Fast Inference**: 0.9 seconds average inference time for classification

### Content Generation
- **BLEU-1 Score**: Achieved 0.13 BLEU-1 score for generated content
- **Generation Speed**: 5.4 seconds average generation time
- **Quality Assessment**: High-quality, contextually relevant content generation

## Technical Implementation

### Model Pipeline
1. **Preprocessing**: Tweet text cleaning and normalization
2. **Classification**: DistilBERT-based categorization
3. **Feature Extraction**: Multi-modal feature engineering
4. **Regression**: Bucket-specific engagement prediction
5. **Generation**: Context-aware content creation

### Optimization Techniques
- **Model Compression**: Optimized for deployment efficiency
- **Batch Processing**: Efficient handling of multiple requests
- **Caching**: Smart caching for frequently accessed data

## Key Innovations

### Multi-Modal Approach
- **Text + Visual**: Combined textual content with visual media analysis
- **Metadata Integration**: Leveraged user profiles and temporal data
- **Cross-Modal Learning**: Learning representations across different data types

### Hierarchical Processing
- **Coarse-to-Fine**: Initial categorization followed by fine-grained analysis
- **Specialized Models**: Bucket-specific models for better accuracy
- **Ensemble Methods**: Combined multiple model predictions

## Technical Stack

- **Deep Learning**: PyTorch, Transformers (DistilBERT, Llama-2)
- **Computer Vision**: BLIP-2 for image understanding
- **Classical ML**: Scikit-learn for regression models
- **Data Processing**: Pandas, NumPy for data manipulation
- **Evaluation**: Custom metrics for social media content assessment

## Impact & Applications

### Real-World Applications
- **Social Media Analytics**: Understanding user engagement patterns
- **Content Strategy**: Optimizing content for better engagement
- **Automated Content Creation**: AI-powered social media management

### Business Value
- **Predictive Insights**: Help brands understand audience behavior
- **Content Optimization**: Improve content creation strategies
- **Engagement Forecasting**: Predict viral content potential

This project showcased the power of combining traditional machine learning with modern transformer architectures to solve complex, multi-modal problems in social media analytics and content generation.