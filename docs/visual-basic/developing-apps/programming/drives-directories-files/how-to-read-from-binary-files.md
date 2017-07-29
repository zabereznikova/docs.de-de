---
title: "Gewusst wie: Lesen von Binärdateien in Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- binary files, reading from
- I/O [Visual Basic], reading from binary files
- ReadAllBytes method, reading from binary files
- My.Computer.FileSystem object, reading from binary files
ms.assetid: d2b1269e-24b6-42e0-9414-ae708db282d8
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f5c0a093073b9a064629ae13a52a2295ad184b81
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-from-binary-files-in-visual-basic"></a>Gewusst wie: Lesen von Binärdateien in Visual Basic
Das `My.Computer.FileSystem`-Objekt bietet die `ReadAllBytes`-Methode zum Lesen von Binärdateien.  
  
### <a name="to-read-from-a-binary-file"></a>Lesen aus einer Binärdatei  
  
-   Verwenden Sie die `ReadAllBytes`-Methode, die den Inhalt einer Datei als Bytearray zurückgibt. In diesem Beispiel wird aus der Datei `C:/Documents and Settings/selfportrait.jpg` gelesen.  
  
     [!code-vb[VbVbcnMyFileSystem#78](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_1.vb)]  
  
-   Für große Binärdateien können Sie die <xref:System.IO.FileStream.Read%2A>-Methode des <xref:System.IO.FileStream>-Objekts verwenden, um nur für einen bestimmten Zeitraum aus der Datei zu lesen. Dann können Sie einschränken, welcher Anteil der Datei für jeden Lesevorgang in den Speicher geladen wird. In folgendem Codebeispiel wird eine Datei kopiert und der Aufrufer kann angeben, wie viel der Datei pro Lesevorgang in den Speicher gelesen wird.  
  
     [!code-vb[VbVbcnMyFileSystem#91](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_2.vb)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können eine Ausnahme auslösen:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, er enthält ungültige Zeichen, oder es handelt sich um einen Gerätepfad (<xref:System.ArgumentException>).  
  
-   Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).  
  
-   Die Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).  
  
-   Die Datei wird von einem anderen Prozess verwendet, oder ein E/A-Fehler tritt auf (<xref:System.IO.IOException>).  
  
-   Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).  
  
-   Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).  
  
-   Es ist nicht genügend Arbeitsspeicher vorhanden, um die Zeichenfolge in den Puffer zu schreiben (<xref:System.OutOfMemoryException>).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).  
  
 Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens. Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei.  
  
 Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden. Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>   
 [Lesen aus Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [Gewusst wie: Lesen aus Textdateien mit mehreren Formaten](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Speichern von Daten in der Zwischenablage und Lesen von Daten aus der Zwischenablage](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md)

