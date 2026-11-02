---
vytvořeno: 2023-11-07T14:28
oddíl: "Pamica - instalace"
zdroj: "OneNote / Návody/Pamica / Pamica - instalace"
tags:
  - onenote-import
  - k-revizi
---
- na počítači, kde chcete instalovat síťového klienta, spusťte z příkazového řádku „cliconfg“
- otevře se Vám níže uvedené dialogové okno, kde povolte „Pojmenované kanály“, „TCP/IP“ a „Protokol sdílený v paměti“

![[Pamica - instalace - image0.png]]

- dále ze sdílené aplikační složky PAMICA spusťte Pamica.exe (Např.: [\\SERVER\PAMICASQL\Pamica.exe](https://outlook.office.com/local/path/file:/SERVER/PAMICASQL/Pamica.exe))
- postupujte dle průvodce
- v případě, že instalace proběhne korektně ale přesto nejde spustit Mzdový systém PAMICA, tak upravte na serveru nastavení Firewallu (je nutné dát výjimku pro Pamica.exe, StwPam.exe, Sqlservr.exe a případně TCP 53897 a UDP 1434) – JIŽ NASTAVENO
