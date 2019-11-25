---
title: 'Vorgehensweise: Erstellen einer Kopie einer Datei im gleichen Verzeichnis'
ms.date: 07/20/2015
f1_keywords:
- File.Copy
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: b2fdda86-e666-42c2-9706-9527e9fa68ff
ms.openlocfilehash: 33a4f5424ac50de7b5dc988034ca15127dc1ed02
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348822"
---
# <a name="how-to-create-a-copy-of-a-file-in-the-same-directory-in-visual-basic"></a>Vorgehensweise: Erstellen einer Kopie einer Datei im gleichen Ordner in Visual Basic

Verwenden Sie die `My.Computer.FileSystem.CopyFile`-Methode, um die Dateien zu kopieren. Die Parameter der Methode bieten die Möglichkeit, vorhandene Dateien zu überschreiben, die Datei umzubenennen, den Fortschritt des Vorgangs anzuzeigen sowie den Benutzer zu erlauben, den Vorgang abzubrechen.  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder"></a>Erstellen einer Kopie einer Datei im gleichen Ordner  
  
- Verwenden Sie die `CopyFile`-Methode, und stellen Sie dabei die Zieldatei und den Speicherort bereit. Im folgenden Beispiel wird eine Kopie von `test.txt` mit dem Namen `test2.txt` erstellt.  
  
     [!code-vb[VbVbcnMyFileSystem#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#51)]  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder-overwriting-existing-files"></a>So erstellen Sie eine Kopie einer Datei im selben Ordner und überschreiben dabei vorhandene Dateien  
  
- Verwenden Sie die `CopyFile`-Methode, stellen Sie die Zieldatei sowie den Speicherort bereit, und setzen Sie `overwrite` auf `True`. Das folgende Beispiel erstellt eine Kopie von `test.txt` mit dem Namen `test2.txt` und überschreibt vorhandene Dateien mit diesem Namen.  
  
     [!code-vb[VbVbcnMyFileSystem#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#52)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Die folgenden Bedingungen können eine Ausnahme auslösen:  
  
- Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).  
  
- Das System konnte den absoluten Pfad nicht abrufen (<xref:System.ArgumentException>).  
  
- Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).  
  
- Die Quelldatei ist ungültig oder nicht vorhanden (<xref:System.IO.FileNotFoundException>).  
  
- Der kombinierte Pfad verweist auf ein vorhandenes Verzeichnis (<xref:System.IO.IOException>).  
  
- Die Zieldatei ist vorhanden und `overwrite` ist auf `False` festgelegt (<xref:System.IO.IOException>).  
  
- Der Benutzer hat keine ausreichende Berechtigungen für den Dateizugriff (<xref:System.IO.IOException>).  
  
- Eine Zielordner mit dem gleichen Namen ist in Gebrauch (<xref:System.IO.IOException>).  
  
- Der Pfad eines Datei- oder Ordnernamens enthält einen Doppelpunkt (:) oder weist ein ungültiges Format auf (<xref:System.NotSupportedException>).  
  
- `ShowUI` ist auf `True` festgelegt, `onUserCancel` ist auf `ThrowException` festgelegt, und der Benutzer hat den Vorgang abgebrochen (<xref:System.OperationCanceledException>).  
  
- `ShowUI` ist auf `True` festgelegt, `onUserCancel` ist auf `ThrowException` festgelegt, und ein nicht angegebener E/A-Fehler tritt auf (<xref:System.OperationCanceledException>).  
  
- Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).  
  
- Der Benutzer verfügt nicht über die erforderliche Berechtigung (<xref:System.UnauthorizedAccessException>).  
  
- Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- [Vorgehensweise: Kopieren von Dateien mit einem bestimmten Muster in ein Verzeichnis](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md)
- [Vorgehensweise: Erstellen einer Kopie einer Datei in einem anderen Verzeichnis](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)
- [Vorgehensweise: Kopieren eines Verzeichnisses in ein anderes Verzeichnis](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)
- [Vorgehensweise: Umbenennen einer Datei](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
