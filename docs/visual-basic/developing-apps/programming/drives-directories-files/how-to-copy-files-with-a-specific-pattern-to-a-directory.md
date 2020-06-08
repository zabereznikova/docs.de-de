---
title: 'Gewusst wie: Kopieren von Dateien mit einem bestimmten Muster in ein Verzeichnis'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: f205d2ad-bbe5-4d55-8a40-acda21aa82dd
ms.openlocfilehash: 7e263e2c9035db54dbb58c6c78c0647d5442504e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401705"
---
# <a name="how-to-copy-files-with-a-specific-pattern-to-a-directory-in-visual-basic"></a>Gewusst wie: Kopieren von Dateien mit einem bestimmten Muster in ein Verzeichnis in Visual Basic

Die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>-Methode gibt eine schreibgeschützte Auflistung von Zeichenfolgen zurück, die die Pfadnamen für die Dateien darstellen. Sie können den `wildCards` -Parameter verwenden, um ein bestimmtes Muster anzugeben.  
  
 Wenn keine übereinstimmenden Dateien gefunden werden, wird eine leere Auflistung zurückgegeben.  
  
 Mit der <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> -Methode können Sie die Dateien in ein Verzeichnis kopieren.  
  
### <a name="to-copy-files-with-a-specific-pattern-to-a-directory"></a>So kopieren Sie Dateien mit einem bestimmten Muster in ein Verzeichnis  
  
1. Verwenden Sie die `GetFiles` -Methode, um die Liste der Dateien zurückzugeben. In diesem Beispiel werden alle RTF-Dateien im angegebenen Verzeichnis zurückgegeben.  
  
     [!code-vb[VbFileIOMisc#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#36)]  
  
2. Verwenden Sie die `CopyFile` -Methode, um die Dateien zu kopieren. In diesem Beispiel werden die Dateien in das Verzeichnis `testdirectory`kopiert.  
  
     [!code-vb[VbVbcnMyFileSystem#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#88)]  
  
3. Schließen Sie die `For` -Anweisung mit einer `Next` -Anweisung.  
  
     [!code-vb[VbVbcnMyFileSystem#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#89)]  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel, das der vollständigen Fassung der oben aufgeführten Codeausschnitte entspricht, werden alle RTF-Dateien im angegebenen Verzeichnis in das Verzeichnis `testdirectory`kopiert.  
  
 [!code-vb[VbFileIOMisc#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#37)]  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  

 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).  
  
- Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).  
  
- Das Verzeichnis ist nicht vorhanden (<xref:System.IO.DirectoryNotFoundException>).  
  
- Das Verzeichnis verweist auf eine vorhandene Datei (<xref:System.IO.IOException>).  
  
- Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).  
  
- Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).  
  
- Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>). Der Benutzer verfügt nicht über die erforderlichen Berechtigungen (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>
- [Gewusst wie: Suchen nach Unterverzeichnissen mit einem bestimmten Muster](how-to-find-subdirectories-with-a-specific-pattern.md)
- [Problembehandlung: Lesen aus und Schreiben in Textdateien](troubleshooting-reading-from-and-writing-to-text-files.md)
- [Gewusst wie: Abrufen einer Sammlung von Dateien in einem Verzeichnis](how-to-get-the-collection-of-files-in-a-directory.md)
