
Modele tylko z pozoru rozumieją nasz tekst. Podążają utartymi schematami co często sprowadza je na manowce. Np przedstawiając  im z pozoru podomny teks do problemu "lisa, żyta i kury" spróbuje rozwiązać ten problem lub próbując wygenerować pokój w którym nie ma słonia.

LangFuse -  pozwala na badanie sprawności oraz estymację kosztów promptów

[TOKENIZER](https://github.com/Microsoft/Tokenizer) - repo z gh tokenizujące od microsoftu

Model może przestać odpisywać z powodu niewystarczającej ilości tokenów co powninniśmy przewidzieć

Moderation API - są to ograniczenia w OpenAI pozwalające ustawić ograniczenia zgodne z polityką firmy [dokumentacja](https://platform.openai.com/docs/guides/moderation/quickstart)


Przy kożystaniu z modelu do oceny jakiejś treści ważne jest aby dać modelowi "czas na zastanowienie się" można to zrobić kożystając np z tagów <thinking>

Modele nie cenzurowane: Dolhin i gork