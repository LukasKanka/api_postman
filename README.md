## Automated API Testing (Postman & Newman)

Automatické testování REST API je postaveno na nástroji [Postman](https://www.postman.com/). Testovací kolekce a prostředí jsou uloženy v repozitáři ve složce `apiTest/PotterAPI` a jsou verzovány společně s kódovým základem.

### Lokální spuštění testů

Testy lze spouštět z grafického rozhraní Postmanu nebo přes příkazovou řádku pomocí nástroje Newman.

#### 1. Pomocí Postman GUI
1. Otevřete aplikaci Postman.
2. Vyberte **Import** a nahrajte soubor kolekce `apiTest/PotterAPI/PotterAPI.postman_collection.json` (a případný soubor prostředí `.postman_environment.json`).
3. Spusťte požadavky jednotlivě nebo celou kolekci přes **Collection Runner**.

#### 2. Pomocí Newman CLI
Ujistěte se, že běží lokální server (standardně na `http://127.0.0.1:3000`), a v terminálu spusťte:

```bash
# Spuštění testů v terminálu
npx newman run apiTest/PotterAPI/PotterAPI.postman_collection.json

# Spuštění testů s vygenerováním HTML reportu (přes newman-reporter-htmlextra)
npx newman run apiTest/PotterAPI/PotterAPI.postman_collection.json \
  -r htmlextra \
  --reporter-htmlextra-export report.html
