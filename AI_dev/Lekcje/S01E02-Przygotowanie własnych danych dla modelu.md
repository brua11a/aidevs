
RAG - Retrieval-Augented Generation

Podczas wyboru danych do LLM musimy pamiętać o ich dostępności i możliwościach modelu. Modele nie są w stanie czytać plików binarnych bezpośrednio np. pdf czy dox. A kiedy te formaty są konwertowana możliwa jest utrata kontekstu danego dokumentu.


Warto preferować format yaml nad json ponieważ zawiera on mniejszą ilość tokenów z perspektywy modelu.

Warto jest dokonywać transformacji danych do bardziej przyjaznych dla modelu formatów.

Musimy pamiętać o kontekście naszego tkstu kiedu chunkujemy go. warto wtedy rozwarzyć oznaczenie poromptów odpowiednim ID.




Projekty do przejżenia: *linear, spotify*