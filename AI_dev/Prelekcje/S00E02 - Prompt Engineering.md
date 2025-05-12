
## Programowanie a AI

W programowaniu Zwykłe czaty potrafią zawodzić ponieważ AI generuje odpowiedzi token po tokenie co generuje pewne problemy. Dlatego OpenAI i inne firmy zastosowało strukturę *ChatML*.

**ChatML** - jest to podział wiadomości na role: Developer, User oraz Assistant które nie zmieniają zasady generowania każdego tokenu po kolei, ale dodaje ona dodatkowe tokeny strukturyzujące 

![[Pasted image 20250508012201.png]]
![[Pasted image 20250508012359.png]]

Kluczowe cechy modelu:
- **Wsparcie języków**
- **Multimodalność**
- **Format API** - Większość modeli posługuje się formatem ChatML
- **Context Window** - liczba tokenów w ramach pojedynczego zapytania
- **Max Output**
- **Knowledge Cutoff**
- **Cena**

## Sterowanie zachowaniem modeli

**Temperatura** - Kreatywność modelu. Jest to zwiększenie prawdopodobieństwa wybrania tokenu który nie koniecznie był na pierwszym miejscu według obliczeń prawdopodobieństwa.

**Top P** - jest to zmienna podobna do temperatury. Jednak jego działanie różni się w ten sposób że ogranicza on ilość tokenów branych pod uwagę.

> Nie zaleca się modyfikacji `Top P` i `temperatury` jednocześnie
> 

[Gemma Scope](https://www.neuronpedia.org/gemma-scope) - narzędzie do reprezentowania budowy wypowiedzi przez AI

Ogólna struktura promptu systemowego:
1. **Zawężenie kontekstu** - polega na nadaniu roli, opisie sytuacji czy problemu w celu uniknięcia dwuznaczności oraz nakierowania model na dany schemat myślenia. Np. "Jesteś programistą JavaScript"
2. **Określenie celu** - może uwzględniać zarówno precyzyjny rezultat lub ogólny kierunek interakcji z modelem. Np. "wypisz listę słów kluczowych w formacie JSON"
3. **Określenie zasad realizacji** - zazwyczaj jest to forma listy (większa czytelność) opisująca zachowanie modelu oraz sposób wykonania zadania.
4. **Dostarczenie informacji** (RAG) - niemal zawsze będzie nam zależało na tym, aby w prompcie systemowym znalazła się sekcja zawierająca dodatkową wiedzę dla modelu (np. istotne wyniki wyszukiwania). Sekcja ta powinna być bardzo wyraźnie oddzielona od pozostałych tak, aby model nie pomylił jej zawartości z instrukcjami, które ma realizować.
5. **Zaprezentowanie przykładów** (Few-shot Prompting) - LLM świetnie rozpoznają wzorce, więc warto poświęcić czas, aby zaprezentować oczekiwane zachowanie na kilku zróżnicowanych przykładach, uwzględniających także warunki brzegowe czy niepożądane scenariusze, które model powinien zaadresować według naszych zasad.

![[Pasted image 20250508015012.png]]


[repozytorium Fabric](https://github.com/danielmiessler/fabric/tree/main/patterns) -przykłady promptów

Schematy promptów:

 - **Zero-Shot**: To prompt zawierający wyłącznie instrukcję
 - **Few-Shot**: To prompt, który poza instrukcją zawiera kilka przykładów w których LLM może zauważyć schematy i wzorce.
 - **Thought Generation**: Czyli ciąg myśli, który może zostać dostarczony przez nas
 - **Ensembling:** Polega na wykorzystaniu wielu promptów lub tego samego promptu wiele razy, aby następnie porównać rezultaty i zdecydować o najbardziej prawdopodobnym wyniku.
 - **Self-reflection:** Polega na stworzeniu przestrzeni dla modelu na wygenerowanie refleksji na temat realizowanego zadania, które poprzedza ostateczną wypowiedź.
 - **Self-criticism**: Jak sugeruje nazwa, to technika polegająca na zastosowaniu LLM w celu krytyki swoich wcześniejszych wypowiedzi.
 - **Decomposition**: To technika opierająca się o rozbijanie trudnych zadań na mniejsze kroki, realizowane zwykle przez oddzielne prompty.

![[Pasted image 20250508015742.png]]

**PromptFoo** -narzędzie do testowania promptów AI. (testy jednostkowe)

```bash
npm i -g promptfoo
promptfoo init
promptfoo init
```

Podczas budowania aplikacji która ma wykorzystać LLM trzeba mieć na uwadze, że model nie zawsze daje poprawne odpowiedzi i nie możemy być na 100% pewni że nie zrobi czegoś źle ale mamy możliwość zwiększenia prawdopodobieństwa poprawnej odpowiedzi poprzez np. Strukturyzację prompta czy few-shot. 