---
title: "How to: Delete a File in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Delete method"
  - "files, deleting"
  - "files, manipulating"
  - "File object"
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Delete a File in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Mit der `DeleteFile`\-Methode des `My.Computer.FileSystem`\-Objekts können Sie Dateien löschen.  Dabei sind u. a. folgende Optionen verfügbar: ob die gelöschte Datei in den **Papierkorb** verschoben werden soll, ob eine Bestätigungsabfrage für den Löschvorgang angezeigt werden soll und was beim Abbrechen des Vorgangs durch den Benutzer geschehen soll.  
  
### So löschen Sie eine Textdatei  
  
-   Verwenden Sie die `DeleteFile`\-Methode, um die Datei zu löschen.  Im folgenden Code wird das Löschen einer Datei mit dem Namen `test.txt` veranschaulicht.  
  
     [!code-vb[VbVbcnMyFileSystem#22](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_1.vb)]  
  
### So löschen Sie eine Textdatei und zeigen eine Bestätigungsabfrage für das Löschen der Datei an  
  
-   Verwenden Sie zum Löschen der Datei die `DeleteFile`\-Methode, und legen Sie `showUI` auf `AllDialogs` fest.  Im folgenden Code wird das Löschen einer Datei mit dem Namen `test.txt` nach dem Anzeigen einer Bestätigungsabfrage veranschaulicht.  
  
     [!code-vb[VbFileIOMisc#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_2.vb)]  
  
### So löschen Sie eine Textdatei und verschieben diese in den Papierkorb  
  
-   Verwenden Sie zum Löschen der Datei die `DeleteFile`\-Methode, und geben Sie für den `recycle`\-Parameter den Wert `SendToRecycleBin` an.  Im folgenden Code wird das Löschen einer Datei mit dem Namen `test.txt` und das Verschieben dieser Datei in den **Papierkorb** veranschaulicht.  
  
     [!code-vb[VbFileIOMisc#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_3.vb)]  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, er enthält ungültige Zeichen, oder es handelt sich um einen Gerätepfad \(beginnt mit \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   Der Pfad ist ungültig, da er `Nothing` ist \(<xref:System.ArgumentNullException>\).  
  
-   Der Pfad überschreitet die im System definierte maximale Länge \(<xref:System.IO.PathTooLongException>\).  
  
-   Ein Datei\- oder Ordnername im Pfad enthält einen Doppelpunkt \(:\) oder hat ein ungültiges Format \(<xref:System.NotSupportedException>\).  
  
-   Die Datei wird gegenwärtig verwendet \(<xref:System.IO.IOException>\).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades \(<xref:System.Security.SecurityException>\).  
  
-   Die Datei ist nicht vorhanden \(<xref:System.IO.FileNotFoundException>\).  
  
-   Der Benutzer verfügt nicht über die erforderliche Berechtigung zum Löschen der Datei, oder die Datei ist schreibgeschützt \(<xref:System.UnauthorizedAccessException>\).  
  
-   Es ist ein teilweise vertrauenswürdiger Kontext vorhanden, in dem der Benutzer nicht über ausreichende Berechtigungen verfügt \(<xref:System.Security.SecurityException>\).  
  
-   Der Benutzer hat den Vorgang abgebrochen, und `onUserCancel` ist auf `ThrowException` festgelegt \(<xref:System.OperationCanceledException>\).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.UIOption>   
 <xref:Microsoft.VisualBasic.FileIO.RecycleOption>   
 [How to: Get the Collection of Files in a Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)