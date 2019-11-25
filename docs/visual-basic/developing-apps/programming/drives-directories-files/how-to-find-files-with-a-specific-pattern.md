---
title: 'Vorgehensweise: Suchen nach Dateien mit einem bestimmten Muster'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], finding
- pattern matching
- patterns, matching
ms.assetid: 25e3b71d-b844-4293-9e4e-f06c5836b5cc
ms.openlocfilehash: 5faaa16615f52714db3de6853786990265716501
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348757"
---
# <a name="how-to-find-files-with-a-specific-pattern-in-visual-basic"></a>Vorgehensweise: Suchen nach Dateien mit einem bestimmten Muster in Visual Basic

Die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>-Methode gibt eine schreibgeschützte Auflistung von Zeichenfolgen zurück, die die Pfadnamen für die Dateien darstellen. Sie können den `wildCards` -Parameter verwenden, um ein bestimmtes Muster anzugeben. Legen Sie zum Einschließen der Unterverzeichnisse in die Suche den Parameter `searchType` auf `SearchOption.SearchAllSubDirectories` fest.  
  
 Es wird eine leere Sammlung zurückgegeben, wenn keine Dateien dem angegebenen Muster entsprechen.  
  
> [!NOTE]
> Informationen zur Rückgabe einer Dateiliste mit der `DirectoryInfo`-Klasse des `System.IO`-Namespace finden Sie unter <xref:System.IO.DirectoryInfo.GetFiles%2A>.  
  
### <a name="to-find-files-with-a-specified-pattern"></a>Suchen nach Dateien mit einem bestimmten Muster  
  
- Verwenden Sie die `GetFiles`-Methode, die den Namen und Pfad des zu durchsuchenden Verzeichnisses bereitstellt, und die das Muster angibt. Im folgenden Beispiel werden alle Dateien mit der Erweiterung `.dll` im Verzeichnis zurückgegeben und `ListBox1` hinzugefügt.  
  
     [!code-vb[VbFileIOMisc#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#4)]  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  

 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).  
  
- Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).  
  
- `directory` ist nicht vorhanden (<xref:System.IO.DirectoryNotFoundException>).  
  
- `directory` verweist auf eine vorhandene Datei (<xref:System.IO.IOException>).  
  
- Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).  
  
- Der Pfad eines Datei- oder Ordnernamens enthält einen Doppelpunkt (:) oder weist ein ungültiges Format auf (<xref:System.NotSupportedException>).  
  
- Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).  
  
- Der Benutzer verfügt nicht über die erforderlichen Berechtigungen (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>
- [Vorgehensweise: Suchen nach Unterverzeichnissen mit einem bestimmten Muster](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)
- [Problembehandlung: Lesen aus und Schreiben in Textdateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
- [Vorgehensweise: Abrufen einer Auflistung der Dateien in einem Verzeichnis](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
