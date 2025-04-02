# Consegna esercizio
Il tuo collega, probabilmente distratto da un gatto o un pappagallo, ha creato una pagina HTML statica invece di utilizzare React come richiesto. La pagina è già online, quindi non possiamo rifarla da zero. Ora tocca a te trasformarla in una meraviglia interattiva usando React, direttamente all’interno del documento HTML. Segui le milestone e dimostra che anche un errore può diventare un’opportunità per brillare!

## Milestone 1: Inserire un Componente React
Monta un componente React all’interno dell’elemento con classe .lista-animali.
Il componente deve includere:
Un elemento <details> con titolo "Animali", che contiene:
Una lista <ul> statica che viene creata a partire da un array di stringhe (animals) dove ciascuna stringa rappresenta il nome di un animale.

Obiettivo: Mostrare la struttura base della lista di animali con un <details> che può essere espanso o contratto.

## Milestone 2: Aggiungere Animali Casuali
1. Trasforma l’array animals usando useState (l’array è inizialmente vuoto).
2. Aggiungi un bottone "Aggiungi Animale" sopra il <details>.
3. Cliccando il bottone, un animale casuale viene aggiunto alla lista.
4. Usa un array predefinito per scegliere casualmente: const animalsChoices = ["Cane", "Gatto", "Pappagallo", "Cavallo", "Panda"];
5. L’animale selezionato deve essere aggiunto all’interno della lista <ul> come <li>.

Obiettivo: L’utente può vedere gli animali aggiunti dinamicamente nella lista.



## Milestone 3: Usare una Modale per Aggiungere Animali
Partendo da questo componente Modal:
function Modal({
      title, 
      content, 
      show = false, 
      onClose = () => {}
  }){
      return show && ReactDOM.createPortal(
          <div className="modal-container">
              <div className="modal">
                  <h2>{title}</h2>
                  <p>{content}</p>
                  <button onClick={onClose}>Annulla</button>
              </div>
          </div>,
          document.body
      )
  }

1. Espandilo affinché:
- La vecchia prop content può essere usata per passare un componente qualsiasi.
- Un nuovo div in fondo alla modale contiene il bottone Annulla e un nuovo bottone Conferma.
- Una nuova prop onConfirm si aspetta una funzione per gestire l’azione di conferma.
2. Sostituisci l’aggiunta casuale dell’animale con una modale interattiva:
- Cliccando il bottone "Aggiungi Animale," si apre una modale.
- La modale include un input di testo (passato al prop content) per inserire il nome di un animale.
- Conferma: Aggiunge l’animale alla lista e chiude la modale.
- Annulla: Chiude la modale senza modificare la lista.

Obiettivo: L’utente può aggiungere animali specifici utilizzando la modale.

