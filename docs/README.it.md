# ⚡ Desktop Organizer

[繁體中文](../README.md) · [简体中文](README.zh-CN.md) · [English](README.en.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Italiano](README.it.md)

## 1.0.7 · 2026-10-05: Nomi per origine e ripristino dei file

Il risultato usa il nome effettivo della cartella di origine: `Download → Download檔案整理資料夾`. Al prossimo riordino, le vecchie cartelle «桌面資料整理» o «桌面整理工具» vengono migrate interamente, conservando contenuti, categorie e relazioni dei percorsi nel registro.

Menu del vassoio → **「檔案回復」 (Ripristina file)** → seleziona la cartella di origine → conferma. Il registro ricostruisce la posizione originale, anche per i file Today, i file riclassificati e le cartelle originali complete. I collegamenti restano al loro posto. Nessuna sovrascrittura in caso di nomi uguali; gli elementi bloccati o non riusciti restano disponibili per un nuovo tentativo. I contenuti senza registro vengono conservati. La cartella dei risultati e gli avvisi generati vengono eliminati solo quando il ripristino è completo e non rimangono contenuti utente. Il registro viene conservato.

Il ripristino sospende solo quella origine, anche dopo il riavvio. «立即整理» riattiva tutte le origini monitorate; la conferma di «整理所選資料夾» riattiva soltanto quella scelta. Se coesistono risultati nuovi e precedenti, il riordino si arresta: ripristina prima, poi riordina. I contenuti privi di registro richiedono intervento manuale.

```text
開啟整理資料夾
────────────
立即整理
暫停自動整理
────────────
整理所選資料夾
檔案回復
────────────
資料夾監視
規則
────────────
查看整理紀錄
版本 1.0.7·檢查更新
────────────
結束
```

## 1.0.6 · 2026-10-05: Menu più ordinato

Apri la cartella organizzata compare per primo. I comandi seguono l’ordine riportato sotto, raggruppati con cinque separatori. La voce della versione mostra dinamicamente quella installata.

```text
開啟整理資料夾
────────────
立即整理
暫停自動整理
────────────
整理所選資料夾
────────────
資料夾監視
規則
────────────
查看整理紀錄
版本 1.0.6·檢查更新
────────────
結束
```


## 1.0.5 · 2026-10-05: Trascina per modificare le categorie

Corregge il trascinamento mancante nell’albero di 1.0.4. Trascina un’estensione come .iso su 程式 per cambiarne l’associazione. Per una categoria scegli 合併關聯 per unire le associazioni alla destinazione, oppure 移為子分類 per mantenerne nome e struttura come sottocategoria. La radice riporta una categoria al livello superiore; trascinare un’estensione su 其他類別 ripristina la classificazione automatica. La destinazione viene evidenziata e i bordi dell’albero consentono lo scorrimento.

Il trascinamento modifica soltanto la bozza. Premi 儲存並重新歸類 e conferma per salvare e riclassificare. Le regole ereditate richiedono l’attivazione delle regole indipendenti prima della modifica. Sono esclusi nodi fissi, la categoria stessa, discendenti ed estensioni come destinazioni. Sottocategorie omonime richiedono un’unione esplicita.

Clic destro sull’icona nell’area di notifica → **“規則” (Regole)**: categorie e associazioni delle estensioni sono mostrate ad albero e si possono aggiungere, modificare o eliminare. Per assegnare ISO ai programmi, seleziona “其他類別 → ISO → .iso”, premi “修改”, scegli “程式” e poi “儲存並重新歸類”. Puoi anche aggiungere direttamente `.iso → 程式`. La tabella seguente mostra le regole predefinite modificabili.

Tutte le origini ereditano le regole condivise. Seleziona il desktop o una cartella monitorata e attiva “此資料夾使用專屬規則” per creare un insieme indipendente a partire da quello condiviso. Le successive modifiche condivise non lo alterano. Disattiva e salva per ripristinare l’eredità. Usa “重新載入” dopo aver modificato l’elenco monitorato. Anche l’organizzazione singola usa le stesse regole per origine.

Il salvataggio chiede conferma delle origini coinvolte, poi riclassifica subito i file già spostati dallo strumento e ancora presenti nelle categorie archiviate. Le cartelle originali in “資料夾” e i file non registrati restano intatti. I file odierni rimangono in Today e usano le nuove regole dopo il cambio di data. Nessuna sovrascrittura; file bloccati e origini offline vengono ritentati. Si rimuovono soltanto le vecchie categorie svuotate. Eliminare una regola non elimina file: i formati senza associazione tornano in “其他類別” per estensione maiuscola. Today e le esclusioni di collegamenti e file temporanei restano fissi. Le impostazioni in `%LOCALAPPDATA%\DesktopOrganizer\sorting-rules.json` sopravvivono a riavvii, aggiornamenti e disinstallazione. Se il file è danneggiato, gli spostamenti si fermano fino alla correzione. [Cronologia](../CHANGELOG.md)

Clic destro sull'icona nel vassoio di Windows → «資料夾監視» (Monitoraggio cartelle) per visualizzare il desktop fisso e aggiungere, modificare o rimuovere altre cartelle. La lista viene conservata dopo il riavvio. Tutte le origini vengono controllate ogni 30 secondi e i risultati rimangono nella rispettiva «XXX檔案整理資料夾». Rimuovere una voce interrompe il monitoraggio senza eliminare dati. Origini offline o in errore non bloccano le altre e vengono riprovate al ritorno. Le cartelle monitorate e i loro antenati restano al loro posto. Le origini aggiuntive non possono duplicarsi o contenersi.

I file in attesa di organizzazione con data locale di ultima modifica odierna vengono raccolti in «當日檔案(Today)», senza distinguere il formato. Al primo controllo dopo il cambio di data, quelli più vecchi passano alle categorie abituali. I file modificati nuovamente oggi restano in Today. Collegamenti e struttura delle sottocartelle originali vengono conservati; i file già archiviati nelle categorie e quelli dentro le sottocartelle originali non vengono riportati in Today.

Pausa e organizzazione immediata si applicano a tutte le origini. Il comando per una singola cartella usa la stessa regola Today: eseguilo di nuovo il giorno successivo oppure aggiungi la cartella al monitoraggio. **1.0.1–1.0.6 possono aggiornarsi via OTA; gli utenti della 1.0.0 devono installare manualmente la 1.0.7.** [Cronologia versioni](../CHANGELOG.md)

> **Spazio alle idee. Un posto per ogni file.**

Report, screenshot, programmi di installazione, archivi. Il desktop merita di essere qualcosa di più di un parcheggio per file.

Desktop Organizer resta nell'area di notifica di Windows, ordina i file singoli per categoria e sposta le cartelle esistenti insieme al loro contenuto. I collegamenti rimangono al loro posto, così puoi continuare a lavorare.

**Avvio all'accesso · Riordino ogni 30 secondi · Collegamenti conservati · Nessuna sovrascrittura · Un solo installer**

## 🚀 Un file. Un nuovo inizio.

Percorso dell'installer, dalla cartella principale del progetto: `bin/DesktopOrganizer-Setup-1.0.7.exe`.

**[⬇️ Scarica l'installer per Windows](https://github.com/jongfat/desktop-file-organizer/raw/refs/heads/main/bin/DesktopOrganizer-Setup-1.0.7.exe)**

1. Fai doppio clic sull'EXE e segui la procedura guidata in cinese tradizionale.
2. Scegli se creare un collegamento sul desktop e avviare il programma all'accesso.
3. Avvia il programma dalla schermata finale oppure dal collegamento in un secondo momento.

Applicazione, icona di avviso, guida e programma di disinstallazione sono inclusi in un unico EXE. Basta copiare questo file su un altro PC per installarlo.

Richiede **Windows 10/11** e **.NET Framework 4.8**. L'installer controlla la presenza del framework e segnala se manca. L'installazione riguarda l'utente corrente, usa come percorso predefinito `%LOCALAPPDATA%\Programs\DesktopOrganizer` e non richiede privilegi di amministratore.

**Le sei lingue riguardano soltanto il README. L'applicazione, l'installer e i nomi effettivi delle cartelle restano in cinese tradizionale. La tabella riporta i nomi reali.**

## 🗂️ Un posto per ogni formato

Tutte le categorie si trovano nella cartella `XXX檔案整理資料夾` sul desktop.

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

> ⚠️ **`XXX檔案整理資料夾` contiene i file originali. Non eliminarla.** L'icona di avviso è un promemoria e non blocca l'eliminazione. Riordinare non significa fare un backup: salva separatamente una copia dei file importanti.

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
