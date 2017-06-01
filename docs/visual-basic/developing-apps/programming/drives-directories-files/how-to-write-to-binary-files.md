---
title: "Vorgehensweise: Schreiben in Binärdateien in Visual Basic | Microsoft-Dokumentation"
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
- files, binary access
- WriteAllBytes method
- binary files, writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0d86e39b7150b4ae8fc4de0498b0b786c5669bb4
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a>Gewusst wie: Schreiben in Binärdateien in Visual Basic
Die Methode <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> schreibt Daten in eine Binärdatei. Wenn der `append`-Parameter `True` ist, fügt er die Daten an die Datei an. Andernfalls werden die Daten in der Datei überschrieben.  
  
 Wenn der angegebene Pfad mit dem Dateinamen nicht zulässig ist, wird eine <xref:System.IO.DirectoryNotFoundException>-Ausnahme ausgelöst. Wenn der Pfad zulässig ist, die Datei aber nicht existiert, wird die Datei erstellt.  
  
### <a name="to-write-to-a-binary-file"></a>Schreiben in eine Binärdatei  
  
-   Verwenden Sie die `WriteAllBytes`-Methode, die den Dateipfad und -namen und die zu schreibenden Bytes bereitstellt. In diesem Beispiel wird das Datenarray `CustomerData` an die Datei `CollectedData.dat` angefügt.  
  
     [!code-vb[VbVbcnMyFileSystem#27](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-to-binary-files_1.vb)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0 (null), der Pfad enthält nur Leerzeichen, oder er enthält ungültige Zeichen. (<xref:System.ArgumentException>).  
  
-   Der Pfad ist ungültig, da er `Nothing` entspricht (<xref:System.ArgumentNullException>).  
  
-   `File` zeigt auf einen Pfad, der nicht existiert (<xref:System.IO.FileNotFoundException> oder <xref:System.IO.DirectoryNotFoundException>).  
  
-   Die Datei wird von einem anderen Prozess verwendet, oder ein E/A-Fehler tritt auf (<xref:System.IO.IOException>).  
  
-   Der Pfad überschreitet die vom System definierte maximale Länge (<xref:System.IO.PathTooLongException>).  
  
-   Der Datei- oder Verzeichnisname im Pfad enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>   
 [Gewusst wie: Schreiben von Text in Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)
