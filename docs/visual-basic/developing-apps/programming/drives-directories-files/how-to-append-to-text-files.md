---
title: "Vorgehensweise: Anfügen an Textdateien in Visual Basic | Microsoft-Dokumentation"
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
- I/O [Visual Basic], appending to files
- I/O [Visual Basic], My.Computer.FileSystem.WriteAllText method
- I/O [Visual Basic], WriteAllText method
ms.assetid: bbbd7fb5-f169-41a9-b53f-520ea9613913
caps.latest.revision: 13
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: eac2d621ba4fe2afebc9eb73f4723c3a869a23a8
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-append-to-text-files-in-visual-basic"></a>Gewusst wie: Anfügen an Textdateien in Visual Basic
Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>-Methode kann verwendet werden, um sie an eine Textdatei anzufügen, indem angegeben wird, dass der `append`-Parameter auf `True` festgelegt wird.  
  
### <a name="to-append-to-a-text-file"></a>Anfügen an eine Textdatei  
  
-   Verwenden Sie die `WriteAllText`-Methode, geben Sie die Zieldatei und die Zeichenfolge an, die angefügt werden sollen, und legen Sie den `append`-Parameter auf `True` fest.  
  
     Dieses Beispiel schreibt die Zeichenfolge `"This is a test string."` in die Datei namens `Testfile.txt`.  
  
     [!code-vb[VbFileIOWrite#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-append-to-text-files_1.vb)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0 (null), er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).  
  
-   Der Pfad ist ungültig, da er `Nothing` entspricht (<xref:System.ArgumentNullException>).  
  
-   `File` zeigt auf einen Pfad, der nicht existiert (<xref:System.IO.FileNotFoundException> oder <xref:System.IO.DirectoryNotFoundException>).  
  
-   Die Datei wird von einem anderen Prozess verwendet, oder ein E/A-Fehler tritt auf (<xref:System.IO.IOException>).  
  
-   Der Pfad überschreitet die vom System definierte maximale Länge (<xref:System.IO.PathTooLongException>).  
  
-   Der Datei- oder Verzeichnisname im Pfad enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 [Schreiben in Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
