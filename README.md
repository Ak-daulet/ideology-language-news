# Ideology, Language & News Subscriptions
### How Political Framing Shapes Reader Conversion Across Major Newspapers (2013–2023)

---

*Read this in: [English](#english-version) | [Русский](#russian-version)*

---

## English Version

### Overview

This project investigates whether the **political orientation of a news outlet** and the **linguistic features of its content** influence the likelihood that a reader will subscribe.

Rather than a simple word-frequency analysis, this is a **behavioral model**: it tests whether ideological alignment between reader and publication — combined with emotionally charged language — drives subscription conversion. It also asks whether this effect intensified after 2016, a year widely associated with accelerating media polarization.

---

### Research Questions

1. Does ideological alignment between reader and outlet increase subscription likelihood?
2. Which lexical patterns (fear, identity, threat, trust) correlate with conversion?
3. Has this effect changed between 2013 and 2023?

---

### Hypotheses

| # | Hypothesis |
|---|------------|
| H1 | Ideological match between reader and outlet increases subscription probability |
| H2 | Emotionally loaded language (fear, threat, identity) increases conversion |
| H3 | Both effects are stronger after 2016 (Trump / Brexit / COVID era) |

---

### Data

#### Outlets by ideological position

| Outlet | Orientation |
|--------|-------------|
| The Guardian | Left / Progressive |
| The New York Times | Center-Left |
| Financial Times | Center / Business |
| The Japan Times | Center |
| The Wall Street Journal | Center-Right |
| NY Post | Right / Populist |

#### Article-level data collected
- Headline text
- Full article body
- Publication date
- Topic category (politics / economy / culture / health)

#### Data sources
- GDELT Project
- Media Cloud
- Kaggle news datasets
- News API (limited historical access)

#### Subscription proxy variables
Since direct subscription data is not publicly available, this project uses academically defensible proxies:

- **Paywall presence** as a binary engagement signal
- **Call-to-action language** ("subscribe", "support journalism")
- **Google Trends** data for outlet-specific subscription queries
- **Survey data** from Pew Research Center (political identity + media consumption)

> **Transparency note:** This is an observational and partially simulated analysis. Correlation does not imply causation. Proxy variables are explicitly documented as approximations.

---

### Methods

#### NLP Pipeline
- TF-IDF vectorization
- Sentiment analysis (VADER, TextBlob)
- Emotion lexicon scoring — NRC Word-Emotion Association Lexicon
- LIWC features (Linguistic Inquiry and Word Count)
- Topic modeling — Latent Dirichlet Allocation (LDA)
- Political framing word lists: *freedom, rights, threat, justice, identity, security*

#### Modeling
- Logistic regression (baseline)
- Random forest classifier
- Feature importance analysis by outlet and time period

---

### Visualizations

- Heatmap of emotional language by outlet and ideology
- Timeline of linguistic shifts 2013–2023
- Probability curves: ideological alignment → subscription likelihood
- NYT vs. WSJ comparative word profiles during key political events
- Topic distribution across the ideological spectrum

---

### Repository Structure

```
📁 ideology-language-subscriptions/
│
├── 📁 data/
│   ├── raw/              # Original collected data
│   ├── processed/        # Cleaned and tokenized text
│   └── proxies/          # Subscription proxy variables
│
├── 📁 notebooks/
│   ├── 01_data_collection.ipynb
│   ├── 02_preprocessing.ipynb
│   ├── 03_sentiment_emotion.ipynb
│   ├── 04_topic_modeling.ipynb
│   ├── 05_modeling.ipynb
│   └── 06_visualization.ipynb
│
├── 📁 src/
│   ├── scraper.py
│   ├── nlp_pipeline.py
│   └── model.py
│
├── 📁 outputs/
│   ├── figures/
│   └── reports/
│
├── requirements.txt
└── README.md
```

---

### Limitations & Ethics

This project is transparent about its constraints:

- No access to real subscriber-level data
- Political orientation simplified to a linear spectrum
- Paywall presence ≠ actual conversion
- Correlation ≠ causation
- Reader ideological preferences are inferred, not measured directly

These limitations are documented at each stage of the analysis.

---

### Skills Demonstrated

`Python` · `NLP` · `Machine Learning` · `Data Visualization` · `Media Analysis` · `Research Design` · `Statistical Modeling`

---

### Status

> **In progress.** Data collection and NLP pipeline under active development.  
> Methodology finalized. Modeling and visualization in progress.

---

### Portfolio Context

This project was developed as part of a research portfolio for graduate school applications in **data journalism and computational social science**. It sits at the intersection of media studies, behavioral economics, and natural language processing.

---

*For questions or collaboration: open an issue or reach out via LinkedIn.*

---
---

## Russian Version

---

# Идеология, язык и подписка на новости
### Как политический фрейминг влияет на конверсию читателей в ведущих мировых изданиях (2013–2023)

---

### О проекте

Этот проект исследует, влияют ли **политическая ориентация издания** и **лингвистические особенности текста** на вероятность того, что читатель оформит платную подписку.

Это не просто частотный анализ слов — это **поведенческая модель**: проверяется гипотеза о том, что идеологическое совпадение между читателем и изданием в сочетании с эмоционально заряженным языком повышает конверсию. Также исследуется, усилился ли этот эффект после 2016 года — переломного момента в медийной поляризации.

---

### Исследовательские вопросы

1. Увеличивает ли идеологическое совпадение читателя и издания вероятность подписки?
2. Какие лексические паттерны (страх, угроза, идентичность, доверие) коррелируют с конверсией?
3. Изменился ли этот эффект в период с 2013 по 2023 год?

---

### Гипотезы

| № | Гипотеза |
|---|----------|
| H1 | Идеологическое совпадение читателя и издания повышает вероятность подписки |
| H2 | Эмоционально нагруженный язык (страх, угроза, идентичность) повышает конверсию |
| H3 | Оба эффекта усиливаются после 2016 года (Трамп / Brexit / COVID) |

---

### Данные

#### Издания по идеологической позиции

| Издание | Ориентация |
|---------|------------|
| The Guardian | Левые / Прогрессивные |
| The New York Times | Центр-левые |
| Financial Times | Центр / Бизнес |
| The Japan Times | Центр |
| The Wall Street Journal | Центр-правые |
| NY Post | Правые / Популистские |

#### Данные на уровне статьи
- Текст заголовка
- Полный текст статьи
- Дата публикации
- Тематика (политика / экономика / культура / здоровье)

#### Источники данных
- GDELT Project
- Media Cloud
- Датасеты Kaggle
- News API (ограниченный исторический доступ)

#### Прокси-переменные для подписки
Поскольку прямые данные о подписках недоступны публично, проект использует академически корректные прокси:

- **Наличие пейволла** как бинарный сигнал вовлечённости
- **Язык призыва к действию** («подпишитесь», «поддержите журналистику»)
- **Google Trends** по запросам, связанным с подпиской на конкретные издания
- **Данные опросов** Pew Research Center (политические взгляды + медиапотребление)

> **Примечание о прозрачности:** Это наблюдательный и частично симулированный анализ. Корреляция не означает причинно-следственной связи. Прокси-переменные задокументированы как приближения.

---

### Методология

#### NLP-пайплайн
- TF-IDF векторизация
- Анализ тональности (VADER, TextBlob)
- Оценка по эмоциональным лексиконам — NRC Word-Emotion Association Lexicon
- LIWC-признаки (Linguistic Inquiry and Word Count)
- Тематическое моделирование — LDA (Latent Dirichlet Allocation)
- Списки слов политического фрейминга: *свобода, права, угроза, справедливость, идентичность, безопасность*

#### Моделирование
- Логистическая регрессия (базовая модель)
- Случайный лес (Random Forest)
- Анализ важности признаков по изданию и временному периоду

---

### Визуализации

- Тепловая карта эмоционального языка по изданию и идеологии
- Временной ряд лингвистических изменений 2013–2023
- Кривые вероятности: идеологическое совпадение → вероятность подписки
- Сравнение NYT и WSJ в ключевые политические моменты
- Распределение тем по идеологическому спектру

---

### Структура репозитория

```
📁 ideology-language-subscriptions/
│
├── 📁 data/
│   ├── raw/              # Исходные данные
│   ├── processed/        # Очищенный и токенизированный текст
│   └── proxies/          # Прокси-переменные подписки
│
├── 📁 notebooks/
│   ├── 01_data_collection.ipynb
│   ├── 02_preprocessing.ipynb
│   ├── 03_sentiment_emotion.ipynb
│   ├── 04_topic_modeling.ipynb
│   ├── 05_modeling.ipynb
│   └── 06_visualization.ipynb
│
├── 📁 src/
│   ├── scraper.py
│   ├── nlp_pipeline.py
│   └── model.py
│
├── 📁 outputs/
│   ├── figures/
│   └── reports/
│
├── requirements.txt
└── README.md
```

---

### Ограничения и этика

Проект открыто документирует свои ограничения:

- Нет доступа к реальным данным о подписчиках
- Политическая ориентация упрощена до линейной шкалы
- Наличие пейволла ≠ реальная конверсия
- Корреляция ≠ причинность
- Идеологические предпочтения читателей выведены косвенно, а не измерены напрямую

Эти ограничения задокументированы на каждом этапе анализа.

---

### Продемонстрированные навыки

`Python` · `NLP` · `Machine Learning` · `Визуализация данных` · `Медиаанализ` · `Дизайн исследования` · `Статистическое моделирование`

---

### Статус проекта

> **В разработке.** Сбор данных и NLP-пайплайн в активной фазе.  
> Методология финализирована. Моделирование и визуализация в процессе.

---

### Контекст портфолио

Проект разработан как часть исследовательского портфолио для поступления в магистратуру по направлениям **дата-журналистика и вычислительные социальные науки**. Он находится на пересечении медиаисследований, поведенческой экономики и обработки естественного языка.

---
## Key Visualization

![NYT Sentiment vs Subscribers](https://raw.githubusercontent.com/Ak-daulet/ideology-language-news/main/nyt_sentiment_subscribers.png)
*По вопросам сотрудничества: откройте issue или напишите через LinkedIn.*
