---
title: 'Gewusst wie: Schreiben von Text in Dateien'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic]
- examples [Visual Basic], text files
ms.assetid: 304956eb-530d-4df7-b48f-9b4d1f2581a0
ms.openlocfilehash: f95a0c4df4a2eab0069a6dab0d4c3fa338d1d8ef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411537"
---
# <a name="how-to-write-text-to-files-in-visual-basic"></a>Gewusst wie: Schreiben von Text in Dateien in Visual Basic

Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>-Methode kann zum Schreiben von Text in Dateien verwendet werden. Ist die angegebene Datei noch nicht vorhanden, wird diese erstellt.  
  
## <a name="procedure"></a>Prozedur  
  
#### <a name="to-write-text-to-a-file"></a>Schreiben von Text in eine Datei  
  
- Verwenden Sie die `WriteAllText`-Methode, um Text in eine Datei zu schreiben, und geben Sie die Datei und den zu schreibenden Text an. In diesem Beispiel wird der Satz `"This is new text."` in die Datei `test.txt` geschrieben und an jeden vorhandenen Text in der Datei angefügt.  
  
     [!code-vb[VbFileIOWrite#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#3)]  
  
#### <a name="to-write-a-series-of-strings-to-a-file"></a>Schreiben von mehreren Zeichenfolgen in eine Datei  
  
- Durchlaufen Sie die Zeichenfolgenauflistung. Verwenden Sie die `WriteAllText`-Methode, um Text in eine Datei zu schreiben, und geben Sie die Zieldatei und die Zeichenfolge an, die angefügt werden soll, und legen Sie den `append`-Parameter auf `True` fest.  
  
     In diesem Beispiel werden die Namen der Dateien im `Documents and Settings`-Verzeichnis in `FileList.txt` geschrieben, und es wird ein Wagenrücklauf zur besseren Lesbarkeit eingefügt.  
  
     [!code-vb[VbFileIOWrite#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#4)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).  
  
- Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).  
  
- `File` verweist auf einen Pfad, der nicht vorhanden ist (<xref:System.IO.FileNotFoundException> oder<xref:System.IO.DirectoryNotFoundException>).  
  
- Die Datei wird von einem anderen Prozess verwendet, oder ein E/A-Fehler tritt auf (<xref:System.IO.IOException>).  
  
- Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).  
  
- Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).  
  
- Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).  
  
- Auf dem Datenträger steht kein Platz mehr zur Verfügung, und der Aufruf von `WriteAllText` schlägt fehl (<xref:System.IO.IOException>).  
  
 Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Code möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen. Weitere Informationen finden Sie unter [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- [Vorgehensweise: Lesen aus Textdateien](how-to-read-from-text-files.md)
