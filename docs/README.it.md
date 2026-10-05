# ⚡ Desktop Organizer

[繁體中文](../README.md) · [简体中文](README.zh-CN.md) · [English](README.en.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Italiano](README.it.md)

> **Spazio alle idee. Un posto per ogni file.**

Report, screenshot, programmi di installazione, archivi. Il desktop merita di essere qualcosa di più di un parcheggio per file.

Desktop Organizer resta nell'area di notifica di Windows, ordina i file singoli per categoria e sposta le cartelle esistenti insieme al loro contenuto. I collegamenti rimangono al loro posto, così puoi continuare a lavorare.

**Avvio all'accesso · Riordino ogni 30 secondi · Collegamenti conservati · Nessuna sovrascrittura · Un solo installer**

## 🚀 Un file. Un nuovo inizio.

Percorso dell'installer, dalla cartella principale del progetto: `bin/DesktopOrganizer-Setup-1.0.0.exe`.

**[⬇️ Scarica l'installer per Windows](../bin/DesktopOrganizer-Setup-1.0.0.exe?raw=true)**

1. Fai doppio clic sull'EXE e segui la procedura guidata in cinese tradizionale.
2. Scegli se creare un collegamento sul desktop e avviare il programma all'accesso.
3. Avvia il programma dalla schermata finale oppure dal collegamento in un secondo momento.

Applicazione, icona di avviso, guida e programma di disinstallazione sono inclusi in un unico EXE. Basta copiare questo file su un altro PC per installarlo.

Richiede **Windows 10/11** e **.NET Framework 4.8**. L'installer controlla la presenza del framework e segnala se manca. L'installazione riguarda l'utente corrente, usa come percorso predefinito `%LOCALAPPDATA%\Programs\DesktopOrganizer` e non richiede privilegi di amministratore.

**Le sei lingue riguardano soltanto il README. L'applicazione, l'installer e i nomi effettivi delle cartelle restano in cinese tradizionale. La tabella riporta i nomi reali.**

## 🗂️ Un posto per ogni formato

Tutte le categorie si trovano nella cartella `桌面資料整理` sul desktop.

| Formato | Destinazione |
| --- | --- |
| DOC, DOCX | 文件 → Word |
| XLS, XLSX, CSV | 文件 → Excel |
| PPT, PPTX | 文件 → PowerPoint |
| PDF / TXT | 文件 → PDF / TXT |
| Immagini come TIF, TIFF, PNG, JPG, JPEG, GIF, WEBP | 圖檔 — immagini |
| Video come MP4, AVI, MOV, MKV, WEBM | 影片 — video |
| Programmi e script come APK, EXE, MSI, MSIX, BAT, CMD, PS1 | 程式 — programmi |
| Archivi come ZIP, RAR, 7Z, TAR, GZ | 壓縮檔 — archivi |
| Cartelle già contenenti file | 資料夾 → nome originale della cartella |
| Altri formati, come LEA | 其他類別 → estensione in maiuscolo |
| Nessuna estensione | 其他類別 → 無副檔名 |

La classificazione usa l'estensione, senza analizzare il testo dei documenti. Non distingue maiuscole e minuscole; con più estensioni considera l'ultima, quindi `backup.tar.gz` finisce negli archivi. Le categorie vengono create solo quando servono.

## 🎛️ Discreto in background. Pronto quando serve.

Il doppio clic sul collegamento del desktop avvia il programma e apre la cartella organizzata. Se il programma è già in esecuzione, apre direttamente la cartella. L'avvio automatico all'accesso avviene in background.

Con il clic destro sull'icona nell'area di notifica puoi riordinare subito, mettere in pausa il riordino automatico, aprire la cartella, consultare il registro o uscire. Anche il doppio clic sull'icona avvia un riordino immediato. La pausa vale per l'esecuzione corrente; uscire non disattiva l'avvio all'accesso.

## 🛡️ Conserva i file. Libera il desktop.

- I collegamenti `.lnk`, `.url` e `.appref-ms` restano sul desktop.
- In caso di nomi uguali, aggiunge `(1)`, `(2)` e così via, senza sovrascrivere file o cartelle.
- Le cartelle esistenti vengono spostate intere, preservando la struttura interna.
- Gli elementi modificati negli ultimi 10 secondi vengono rinviati. Gli spostamenti falliti sono registrati e ritentati nei cicli successivi.
- Salta elementi nascosti, di sistema, collegati, i comuni download temporanei e i file temporanei di Office. Non sposta gli elementi del desktop pubblico.
- Il registro è in `%LOCALAPPDATA%\DesktopOrganizer\history.csv`: `MOVE` indica un tentativo, `DONE` il completamento ed `ERROR` un errore.

Usa il percorso del desktop dell'utente configurato in Windows, anche se reindirizzato a OneDrive. L'avvio automatico avviene quando accedi a Windows.

> ⚠️ **`桌面資料整理` contiene i file originali. Non eliminarla.** L'icona di avviso è un promemoria e non blocca l'eliminazione. Riordinare non significa fare un backup: salva separatamente una copia dei file importanti.

## 🔄 Aggiornare, disattivare o disinstallare

Prima di aggiornare, esci dall'area di notifica e avvia il nuovo installer. Le vecchie categorie vengono adattate alle regole attuali; quelle svuotate vengono rimosse, mentre gli elementi non spostati restano disponibili per un nuovo tentativo.

Per disattivare l'avvio automatico, premi `Win + R`, digita `shell:startup` ed elimina il collegamento `桌面整理工具`. Chiudi anche il programma attualmente in esecuzione.

Per disinstallare, esci prima dal programma, poi usa le app installate di Windows o il menu Start. I file dell'applicazione e i collegamenti creati dall'installer vengono rimossi; **i dati organizzati e i registri rimangono**. Metti in pausa o chiudi il programma prima di riportare manualmente i file sul desktop.

## 🧰 Compilazione e creazione del pacchetto

Questo repository GitHub di distribuzione contiene l'installer e la documentazione. I comandi seguenti si riferiscono al progetto di sviluppo locale completo.

Realizzato con C#, Windows Forms, .NET Framework e Inno Setup 6. Esegui dalla cartella principale del progetto:

```powershell
./build.ps1           # Compila il programma e genera l'icona
./test.ps1            # Verifica classificazione, spostamenti e migrazioni
./build-installer.ps1 # Genera un unico installer EXE in bin
./test-installer.ps1  # Verifica installazione, aggiornamento, rimozione e dati
```

Il compilatore predefinito è `.tools/InnoSetup/ISCC.exe`; usa `-CompilerPath` per specificarne un altro.

Per l'installazione di sviluppo usa `./install.ps1` oppure `./install.ps1 -Update`. Il percorso predefinito è `%LOCALAPPDATA%\DesktopOrganizer`; durante l'aggiornamento viene riutilizzata la posizione del collegamento esistente. È un metodo distinto dalla procedura guidata.

Il pacchetto contiene soltanto applicazione, configurazione, icona e guida. Attualmente Git ignora `bin`; puoi caricare l'EXE generato su GitHub Releases per distribuirlo.
