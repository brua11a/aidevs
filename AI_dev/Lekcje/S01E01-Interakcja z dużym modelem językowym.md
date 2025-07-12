
#### Modele ogólnego zastosowania:
- OpenAI: Modele z rodziny o1, GPT, w tym także TTS, Whisper i Embedding
- Anthropic: Modele z rodziny Claude (tylko tekst + obraz)
- Vertex AI (Google): Modele Gemini oraz wybranych dostawców (np. Anthropic) i inne
- [xAI](https://accounts.x.ai/): Modele Grok, które dość szybko przebiły się na szczyty rankingów (top10).
- Amazon Bedrock (Amazon): Modele Anthropic, Mistral czy Meta i inne
- Azure (Microsoft): Modele OpenAI, Meta i inne
- Groq: Modele Open Source, np. Llama
- a także kilka innych, np.: OpenRouter, Perplexity, Cerebras, Databricks, Mistral AI czy Together AI

![Automatyzacja w połączeniu z dużym modelem językowym pozwala na dość swobodne transformowanie różnych formatów treści, a także dynamiczne dostosowanie się do sytuacji](https://cloud.overment.com/2024-09-02/aidevs_agent-e32d845c-6.png)

Dzięki agentom Ai możemy zastąpić rozbudowane regexy potrzebne do analizy inputu oraz jesteśmy w stanie przyjmować dane z różnych źródeł bez potrzeby dobudowania zaawansowanych regexów.

Wygenerowanie rezultatu polega na przejściu przez 4 kroki:
1. Zrozumienie wymagające wczytania pamięci, zapytania do internetu. W ten sposób dajemy modelowi dane spoza jego wiedzy.
2. Plan działania wymagający "przemyśleń" połączonych z listą dostępnych narzędzi, umiejętności lub innych agentów.
3. Podejmowanie działań - Model wykonuje stworzony plan i podejmuje decyzję w zależności od rezultatów
4. Odpowiedź ostateczny rezultat z podjętych działań

![[Pasted image 20250628180436.png]]

Programowa interakcja z modelem polega na budowaniu tabeli messages. Jednak zamiast przekazywać wszystkich wysłanych wiadomości możemy ograniczyć się jedynie do podsumowania konwersacji wygenerowanego przez model.

Podczas wyszukiwania w internecie ważnym jest by ograniczyć listę domen które zostają przeszukane by ograniczyć ilość słabej jakości informacji i stron wymagających logowania.


![[Pasted image 20250628184953.png]]

Przy optymalizacji modelu warto zwiąć pod uwagę podanie przykładów od ~3-40 by pomóc w pracy modelu.

Przykłady kodu: *pick_domains, use_search, thread, rate, websearch*, S00E02 PromptFoo
