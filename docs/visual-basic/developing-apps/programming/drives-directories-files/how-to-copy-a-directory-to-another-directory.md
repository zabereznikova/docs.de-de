---
title: "How to: Copy a Directory to Another Directory in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "I/O [Visual Basic], copying directories"
  - "I/O [Visual Basic], copying folders"
  - "folders [Visual Basic], copying"
  - "directories [Visual Basic], copying"
ms.assetid: 2a370bd7-10ba-4219-afc4-4519d031eb6c
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# How to: Copy a Directory to Another Directory in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Verwenden Sie die <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A>, um ein Verzeichnis in ein anderes Verzeichnis zu kopieren.  Diese Methode kopiert den Inhalt des Verzeichnisses sowie das Verzeichnis selbst.  Wenn das Zielverzeichnis nicht vorhanden ist, wird dieses erstellt.  Wenn am Zielort ein Verzeichnis mit dem gleichen Namen vorhanden ist und `overwrite` auf `False` festgelegt ist, wird der Inhalt der beiden Verzeichnisse zusammengeführt.  Sie können während des Vorgangs einen neuen Namen für das Verzeichnis angeben.  
  
 Beim Kopieren von Dateien innerhalb eines Verzeichnisses werden möglicherweise Ausnahmen durch eine bestimmte Datei ausgelöst, beispielsweise wenn `overwrite` auf `False` festgelegt ist und eine Datei während einer Zusammenführung vorhanden war.  Wenn solche Ausnahmen ausgelöst werden, werden sie in eine einzelne Ausnahme konsolidiert, deren `Data`\-Eigenschaft Einträge enthält, in denen die Datei oder der Verzeichnispfad der Schlüssel und die jeweilige Ausnahmemeldung im zugehörigen Wert enthalten ist.  
  
### So kopieren Sie ein Verzeichnis in ein anderes Verzeichnis  
  
-   Verwenden Sie die `CopyDirectory`\-Methode, und geben Sie die Quell\- und Zielverzeichnisnamen an.  Im folgenden Beispiel wird das Verzeichnis mit dem Namen `TestDirectory1` in das Verzeichnis `TestDirectory2` kopiert, wobei vorhandene Dateien überschrieben werden.  
  
     [!code-vb[VbVbcnMyFileSystem#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-a-directory-to-another-directory_1.vb)]  
  
     Dieses Codebeispiel ist auch als IntelliSense\-Codeausschnitt verfügbar.  In der Codeausschnittauswahl finden Sie es unter **Dateisystem \- Verarbeiten von Laufwerken, Ordnern und Dateien**.  Weitere Informationen finden Sie unter [Codeausschnitte](/visual-studio/ide/code-snippets).  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Der für das Verzeichnis angegebene neue Name enthält einen Doppelpunkt \(:\) oder einen Schrägstrich \(\\ oder \/\) \(<xref:System.ArgumentException>\).  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, er enthält ungültige Zeichen, oder es handelt sich um einen Gerätepfad \(beginnt mit \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   Der Pfad ist ungültig, da er `Nothing` ist \(<xref:System.ArgumentNullException>\).  
  
-   `destinationDirectoryName` ist `Nothing` oder eine leere Zeichenfolge \(<xref:System.ArgumentNullException>\).  
  
-   Das Quellverzeichnis ist nicht vorhanden \(<xref:System.IO.DirectoryNotFoundException>\).  
  
-   Das Quellverzeichnis ist ein Stammverzeichnis \(<xref:System.IO.IOException>\).  
  
-   Der kombinierte Pfad zeigt auf eine vorhandene Datei \(<xref:System.IO.IOException>\).  
  
-   Der Quellpfad und der Zielpfad sind identisch \(<xref:System.IO.IOException>\).  
  
-   `ShowUI` ist auf `UIOption.AllDialogs` festgelegt, und der Vorgang wird vom Benutzer abgebrochen, oder mindestens eine Datei im Verzeichnis kann nicht kopiert werden \(<xref:System.OperationCanceledException>\).  
  
-   Der Vorgang ist zyklisch \(<xref:System.InvalidOperationException>\).  
  
-   Der Pfad enthält einen Doppelpunkt \(:\) \(<xref:System.NotSupportedException>\).  
  
-   Der Pfad überschreitet die im System definierte maximale Länge \(<xref:System.IO.PathTooLongException>\).  
  
-   Ein Datei\- oder Ordnername im Pfad enthält einen Doppelpunkt \(:\) oder hat ein ungültiges Format \(<xref:System.NotSupportedException>\).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades \(<xref:System.Security.SecurityException>\).  
  
-   Eine Zieldatei ist vorhanden, aber es ist kein Zugriff auf die Datei möglich \(<xref:System.UnauthorizedAccessException>\).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A>   
 [How to: Find Subdirectories with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)   
 [How to: Get the Collection of Files in a Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)