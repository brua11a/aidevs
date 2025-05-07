#Ogólne

Modele LLM są swojego rodzaju black boxem. Są niedeterministyczne i opierają się na prawdopodobieństwie.  Kolejne tokeny są generowane poprzez prawdopodobieństwo ich wystąpienia biorąc pod uwagę input oraz wcześniej wygenerowane tokeny.

![[Pasted image 20250508005827.png]]

**sieci neuronowe** - złożone struktury wzorowane na ludzkim mózgu. Ich główne komponenty definiowane są przez ludzi, jednak sam sposób działania jest kształtowany podczas kilkuetapowego treningu.

[Mapping the Mind of a Large Language Model](https://www.anthropic.com/news/mapping-mind-language-model) - przedstawia przełomowe badania nad interpretowalnością dużych modeli językowych (LLM), takich jak Claude Sonnet

[Tiktokenizer](https://tiktokenizer.vercel.app/)

Modele lepiej radzą sobie z językiem angielskim także pod tym względem że słowa angielskie są rozbijane na mniejszą ilość tokenów.

**RAG**  (Retrieval-Augmented Generation) - własna baza wiedzy

![[Pasted image 20250508011245.png]]
![[Pasted image 20250508011311.png]]

Przykładowy kod do łączenia z API
```python
import requests

url = "https://poligon.aidevs.pl/dane.txt"
response = requests.get(url)

if response.status_code == 200:
	print(response.text)
else:
	print(f"Błąd: {response.status_code}")
	
tmp = response.text.split()
payload = { "task": "POLIGON", "apikey": "-API- key",
			"answer": [ tmp[0], tmp[1] ] }
			
url = "https://poligon.aidevs.pl/verify"
response = requests.post(url, json=payload) 

if response.status_code == 200: 
	print("Odpowiedź z serwera:", response.json())
else:
	print(f"Błąd: {response.status_code}")
```
