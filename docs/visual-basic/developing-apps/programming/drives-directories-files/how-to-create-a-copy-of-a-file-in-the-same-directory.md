---
title: "How to: Create a Copy of a File in the Same Directory in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "File.Copy"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]"
  - "files, copying"
  - "CopyFile method, copying files in Visual Basic"
  - "I/O [Visual Basic], copying files"
ms.assetid: b2fdda86-e666-42c2-9706-9527e9fa68ff
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Create a Copy of a File in the Same Directory in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Verwenden Sie die `My.Computer.FileSystem.CopyFile`\-Methode, um die Dateien zu kopieren.  Dabei können Sie verschiedene Parameter angeben, beispielsweise um vorhandene Dateien zu überschreiben, die Datei umzubenennen, den Fortschritt des Vorgangs anzuzeigen und dem Benutzer den Abbruch des Vorgangs zu erlauben.  
  
### So erstellen Sie eine Kopie einer Datei im gleichen Ordner  
  
-   Verwenden Sie die `CopyFile`\-Methode, und geben Sie die Zieldatei und den Zielspeicherort an.  Im folgenden Beispiel wird eine Kopie von `test.txt` mit dem Namen `test2.txt` erstellt.  
  
     [!code-vb[VbVbcnMyFileSystem#51](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-_0_1.vb)]  
  
### So erstellen Sie eine Kopie einer Datei im gleichen Ordner und überschreiben vorhandene Dateien  
  
-   Verwenden Sie die `CopyFile`\-Methode. Geben Sie dabei die Zieldatei und den Speicherort an, und legen Sie `overwrite` auf `True` fest.  Im folgenden Beispiel wird eine Kopie von `test.txt` mit dem Namen `test2.txt` erstellt, wobei vorhandene Dateien mit diesem Namen überschrieben werden.  
  
     [!code-vb[VbVbcnMyFileSystem#52](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-_0_2.vb)]  
  
## Robuste Programmierung  
 Die folgenden Bedingungen verursachen möglicherweise das Auslösen einer Ausnahme:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, er enthält ungültige Zeichen, oder es handelt sich um einen Gerätepfad \(beginnt mit \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   Das System konnte den absoluten Pfad nicht abrufen \(<xref:System.ArgumentException>\).  
  
-   Der Pfad ist ungültig, da er `Nothing` ist \(<xref:System.ArgumentNullException>\).  
  
-   Die Quelldatei ist ungültig oder nicht vorhanden \(<xref:System.IO.FileNotFoundException>\).  
  
-   Der kombinierte Pfad zeigt auf ein vorhandenes Verzeichnis \(<xref:System.IO.IOException>\).  
  
-   Die Zieldatei ist bereits vorhanden, und `overwrite` ist auf `False` festgelegt \(<xref:System.IO.IOException>\).  
  
-   Der Benutzer verfügt nicht über ausreichende Berechtigungen für den Zugriff auf die Datei \(<xref:System.IO.IOException>\).  
  
-   Eine Datei im Zielordner mit demselben Namen wird gegenwärtig verwendet \(<xref:System.IO.IOException>\).  
  
-   Ein Datei\- oder Ordnername im Pfad enthält einen Doppelpunkt \(:\) oder hat ein ungültiges Format \(<xref:System.NotSupportedException>\).  
  
-   `ShowUI` ist auf `True` festgelegt, `onUserCancel` ist auf `ThrowException` festgelegt, und der Benutzer hat den Vorgang abgebrochen \(<xref:System.OperationCanceledException>\).  
  
-   `ShowUI` ist auf `True` festgelegt, `onUserCancel` ist auf `ThrowException` festgelegt, und ein nicht näher bezeichneter E\/A\-Fehler ist aufgetreten \(<xref:System.OperationCanceledException>\).  
  
-   Der Pfad überschreitet die im System definierte maximale Länge \(<xref:System.IO.PathTooLongException>\).  
  
-   Der Benutzer verfügt nicht über die erforderliche Berechtigung \(<xref:System.UnauthorizedAccessException>\).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades \(<xref:System.Security.SecurityException>\).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>   
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>   
 [Gewusst wie: Kopieren von Dateien mit einem bestimmten Muster in ein Verzeichnis](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md)   
 [How to: Create a Copy of a File in a Different Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)   
 [How to: Copy a Directory to Another Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)   
 [How to: Rename a File](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)