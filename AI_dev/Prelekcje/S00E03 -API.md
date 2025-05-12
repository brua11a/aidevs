Używając API bierzemy pod uwagę to że wykonywanie wielu zapytań zależnych od siebie zmniejsza prawdopodobieństwo uzyskania dobrego wyniku w ostatnim kroku, a popełnianie błędów we wcześniejszym etapie znacznie zmniejsza prawdopodobieństwo uzyskania dobrego wyniku.

**frequency_penalty** — obniża prawdopodobieństwo wystąpienia danego tokenu, poprzez nakładanie na niego kary uzależnionej od tego, ile razu został już wybrany w dotychczas generowanej treści.  
  
**presence_penalty** — podobnie jak frequency_penalty obniża prawdopodobieństwo wybrania tokenu, ale kara jest uzależniona od samej obecności tokenu, a nie tego, ile razy się pojawił.

**logit_bias** — umożliwia podanie ID tokenu oraz wartości z zakresu -100 - 100. Wartość -100 wyklucza token, a 100 niemal wymusza jego użycie. Identyfikatory tokenów można znaleźć dzięki Tiktokenizer i będą się one różnić w zależności od tokenizera wykorzystywanego przez model.

**stop** — to lista maksymalnie czterech sekwencji, które zatrzymają dalsze generowanie wypowiedzi

**n —** określa liczbę generowanych odpowiedzi dla tego samego promptu. To użyteczny parametr w przypadku Self-Consistency (technika polegająca na wybieraniu najlepszego rezultatu spośród kilku wariantów)

**user —** to ID użytkownika z naszej bazy, które pozwoli na zidentyfikowanie zapytań pochodzących od niego. To jedno z zaleceń [dobrych praktyk na produkcji](https://platform.openai.com/docs/guides/production-best-practices), rekomendowanych przez OpenAI.


Uruchomienie ollama:
```bash
ollama run gemma2:2b
```

[Unsloth](https://unsloth.ai/) - narzędzie do fine-tuningu

Modele na które warto zwrócić uwagę to llama 3.1, gemma 2, qwen2, phi3, mistral, deepseek coder, llava (vision), MiniCPM (vision) i whisper (speech to text), ChatTTS (text to speech)