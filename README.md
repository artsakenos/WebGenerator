# WebGenerator

WebGenerator è una roba magica che ti permette di creare siti fighetti con testo autogenerato.
Ogni volta che il sito (un sito statico a tua scelta) viene ricaricato, i nuovi contenuti sono generati in base
ad una grammatica (che sta su un file di testo) da te compilata.

USAGE
=====
Webgenerator si installa con un Docker (se non lo conosci, [un docker client si installa](https://docs.docker.com/install/) con tipo due / tre comandi).

1. Clona questo repository: `git clone https://github.com/artsakenos/WebGenerator.git`
2. Modifica la grammatica [wg_grammar.txt](https://github.com/artsakenos/WebGenerator/blob/master/wg_grammar.txt) a tuo piacimento, segui le istruzioni al suo interno
3. Modifica il sito a tuo piacimento, segui l'esempio del [template](https://github.com/artsakenos/WebGenerator/tree/master/wg_site) o utilizza qualsiasi template di tuo gradimento, ricordando che:
    * L'entry point del sito è un `index.html`, e il tutto deve essere confezionato dentro `wg_site/*`.
    * Ricorda di impostare i markup per la sostituzione del testo come spiegato nella grammatica
4. Compila il tuo docker container: `docker build -f webgenerator.docker -t webgenerator:il_mio_wg_personalizzato .`
5. Avvia il tuo container: `docker run -it --rm -d -p 8085:8085 webgenerator:il_mio_wg_personalizzato`

Il container apre un server web che espone la porta 8085, ma puoi inoltrarlo dove preferisci, e.g., 80:8085.

Buon divertimento.
