---
title: 'Gewusst wie: Verschieben von Dateien'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], moving
ms.assetid: 53a7457b-5815-41ad-b37d-28537c1fb77a
ms.openlocfilehash: 2dafeb3b5f8b8c3a8976b25c1a57f405aebb32b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401601"
---
# <a name="how-to-move-a-file-in-visual-basic"></a>Gewusst wie: Verschieben von Dateien in Visual Basic

Mit der `My.Computer.FileSystem.MoveFile` -Methode kann eine Datei in einen anderen Ordner verschoben werden. Wenn die Zielstruktur nicht vorhanden ist, wird sie erstellt.  
  
### <a name="to-move-a-file"></a>So verschieben Sie eine Datei  
  
- Verwenden Sie zum Verschieben der Datei die `MoveFile` -Methode,wobei Sie sowohl für die Quelldatei als auch für die Zieldatei deren Namen und Speicherort angeben. In diesem Beispiel wird die Datei `test.txt` aus `TestDir1` in `TestDir2`verschoben. Beachten Sie, dass der Name der Zieldatei angegeben ist, obwohl er mit dem Namen der Quelldatei identisch ist.  
  
     [!code-vb[VbVbcnMyFileSystem#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#24)]  
  
### <a name="to-move-a-file-and-rename-it"></a>So verschieben Sie eine Datei und benennen diese um  
  
- Verwenden Sie zum Verschieben der Datei die `MoveFile` -Methode, wobei Sie den Namen und den Speicherort der Quelldatei, den Zielspeicherort sowie den neuen Namen angeben, der am Zielspeicherort verwendet werden soll. In diesem Beispiel wird die Datei `test.txt` aus `TestDir1` in `TestDir2` verschoben und in `nexttest.txt`umbenannt.  
  
     [!code-vb[VbVbcnMyFileSystem#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#25)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).  
  
- Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).  
  
- `destinationFileName` ist `Nothing` oder eine leere Zeichenfolge (<xref:System.ArgumentNullException>).  
  
- Die Quelldatei ist ungültig oder nicht vorhanden (<xref:System.IO.FileNotFoundException>).  
  
- Der kombinierte Pfad zeigt auf ein vorhandenes Verzeichnis, die Zieldatei ist vorhanden, und `overwrite` ist auf `False`festgelegt, eine Datei im Zielverzeichnis mit demselben Namen wird derzeit verwendet, oder der Benutzer hat keine ausreichenden Berechtigungen, um auf die Datei zuzugreifen (<xref:System.IO.IOException>).  
  
- Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).  
  
- `showUI` ist auf `True`festgelegt, `onUserCancel` ist auf `ThrowException`festgelegt, und entweder der Benutzer hat den Vorgang abgebrochen, oder es tritt ein nicht näher angegebener E/A-Fehler auf (<xref:System.OperationCanceledException>).  
  
- Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).  
  
- Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).  
  
- Der Benutzer hat nicht die erforderliche Berechtigung (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.MoveFile%2A>
- [Gewusst wie: Umbenennen einer Datei](how-to-rename-a-file.md)
- [Gewusst wie: Erstellen einer Kopie einer Datei in einem anderen Verzeichnis](how-to-create-a-copy-of-a-file-in-a-different-directory.md)
- [Gewusst wie: Analysieren von Dateipfaden](how-to-parse-file-paths.md)
