## Clonazione Progetto Laravel Già avviato

1. Clonare sul pc il progetto da github
2. Apriamo il progetto con VS Code
3. Creiamo dentro il progetto un nuovo file 📃 .env
4. Copiamo e incolliamo dentro il file 📃 .env il contenuto di .env.example
5. Apriamo il terminale nel progetto e lanciamo il comando: ```composer install``` ( Se escono errori passiamo al comando: ```composer update``` )
6. Lanciamo poi il comando: ```php artisan key:generate```
7. Installiamo le dipendenze di Node con il comando: ```npm install```
8. Al termine possiamo attivare il server con il comando: ```php artisan serve```

## Creare file fake database nella cartella config e richiamarlo nella rotta

1. Creare un array multidimensionale con dentro array associativi
2. Inserire l'array nella 📁 config e anzichè nominare l'array muldimensionale mettere un "return" all'inizio
```
//config/pasta.php
<?php
return [
    [
        "src" => "https://www.lamolisana.it/wp-content/uploads/2021/09/4-spaghetto-quadrato-bucato.jpg",
        "src-h" => "https://www.lamolisana.it/wp-content/uploads/2021/09/4-spaghetto-quadrato-bucato.png",
        "src-p" => "https://www.lamolisana.it/wp-content/uploads/2021/09/spaghetto-quadrato-bucato.jpg",
        "titolo" => "N.4 Spaghetto Quadrato Bucato",
        "tipo" => "lunga",
        "cottura" => "6 min",
        "peso" => "500g",
        "descrizione" => "È la vera rivelazione della gamma! Lo Spaghetto Quadrato Bucato n.4 fa pensare subito ad una pasta molto succulenta che ha lo stesso potenziale dello Spaghetto Quadrato (N.1 Spaghetto Quadrato). La sua consistenza soda si sprigiona in bocca con un’esplosione di emozioni, grazie agli spessori corposi, al colore elegantemente ambrato, alla texture delicatamente ruvida, cangiante e piacevolissima al tatto che trattiene il condimento sulla superficie. <br> Da provare per rivoluzionare le sorti del primo piatto sia a casa che al ristorante.Dedicato a chi in cucina ama sperimentare nuove forme del gusto, ma vuole stupire affidandosi ad una pasta che garantisce ottime performance in cottura, lo Spaghetto Quadrato Bucato n .4 è il formato perfetto che racchiude tutte caratteristiche uniche di Pasta La Molisana. <br> Da provare per quelli che… il Bucatino già mi piace, lo Spaghetto Quadrato Bucato n .4 sarà il paradiso della pasta!"
    ],
...
];
?>
```

3. Nel 📃web.php importare il file in una variabile: ``` $pasta = config('pasta'); ```
4. Impostare il return della rotta get così per associazione chiave => valore: ``` return view('prodotti', ['products' => $pasta] ); ```

## Iniziare progetto laravel 7 da zero

1. Aprire vs code, entrare nella cartella dove lanciare il progetto e lanciare da terminale il comando:
```composer create-project --prefer-dist laravel/laravel:^7.0 [NOME PROGETTO]```
2. Entriamo nella cartella progetto e lanciamo i comandi per creare la repository:
   1. Creare una Repository direttamente sul profilo personale di Github
   2. Aprire il terminale preferito e spostarsi nella cartella di lavoro che si vuole inizializzare come repository
   3. Utilizzare il comando ``` git init ```
   4. Poi il comando ```git add -A ```
   5. Poi il comando ```git commit -m " Testo del commit " ```
   6. Poi il comando ```git remote add origin .........URL DELLA REPO........```
   7. Poi il secondo comando ```git push -u origin master```
3. Se vogliamo utilizzare Sass:
    1. Lanciamo da terminale il comando: ```npm i```
    2. Poi il comando: ```npm run dev```
    3. Poi il comando: ```npm run watch```
    4. Per gestire gli url delle immagini caricate in sass, modificare il file 📃 webpack.mix.js aggiungendo le options in questo modo:
    ```
    mix.js('resources/js/app.js', 'public/js')
        .sass('resources/sass/app.scss', 'public/css')
        .options({
        processCssUrls: false});
    ```
4. Per attivare il progetto lanciare il comando: ```php artisan serve```

## Installare node_modules per usare dipendenze NPM
1. Lanciare il comando da terminale: ```npm install```

## Pulire la cache della cartella config
1. Se modifichiamo i file della cartella config dobbiamo lanciare il comando: ```php artisan config:clear```

## Creare la tabella con le rotte create in laravel
1. Lanciamo il comando da terminale: ```php artisan route:list```

## Pulire la cache di laravel
1. lanciamo il comando da terminale: ```php artisan cache:clear```

## Pulire la cache di npm
1. lanciamo il comando da terminale: ```npm cache clear --force``` (utile se ```npm install``` non funziona)

## fontawesome
1. Lanciare d aterminale il comando: ```npm install @fortawesome/fontawesome-free```
2. Inserire l'import nel file 📃app.scss : ```@import '~@fortawesome/fontawesome-free/css/all.css';```
3. Lanciare d aterminale il comando: ```npm run dev```
4. Inserire un icona free di prova

## importare bootstrap 5 in laravel 7
A. Lanciare il comando se non ancora fatto: ```npm i```
1. Lanciare il comando da terminale: ```npm install bootstrap```
2. Lanciare il comando da terminale: ```npm i @popperjs/core```
3. Aprire il file 📃app.scss e inserire:
```
@import '~bootstrap/dist/css/bootstrap.min.css';
```
4. Andare nel file app.js nella cartella resources e inserire:
```
import '../../node_modules/@popperjs/core/dist/umd/popper.min.js';
import 'bootstrap/js/dist/dropdown';
```
5. Lanciare da terminale il comando (per generare files css e js nella cartella public): ```npm run dev```
6. Creare nella view del layout il collegamento ai file compilati da webpack.mix.js:
```
<link rel="stylesheet" href=" {{ asset('css/app.css') }} ">

<script src=" {{ asset('js/app.js') }} "></script>
```
7. Rilanciare d azero il comando da terminale: ```npm run watch```
8. Usare le classi di bootstrap 5 nelle views

## Creare e gestire la prima rotta

1. aprire il file web.php
2. Da terminale lanciare il comando: ```php artisan make:controller [NomeCOntroller]```
2. creiamo la struttura della rotta sulla base del controller:
```
Route::get('/', 'PageController@index' )->name('home');
```


## Stampare tabella nel terminale per leggere le liste
1. lanciare da terminale il comando: ```php artisan route:list```

## creare un model

1. aprire il terminale e lanciare il comando: ```php artisan make:model Models/[NomeModello]```
