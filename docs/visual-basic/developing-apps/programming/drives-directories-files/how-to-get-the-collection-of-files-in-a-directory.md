---
title: 'Gewusst wie: Abrufen einer Auflistung der Dateien in einem Verzeichnis'
ms.date: 07/20/2015
helpviewer_keywords:
- folders, working with
- files [Visual Basic], accessing
ms.assetid: 6c8ba7e8-dd37-4853-92bf-762b67c98160
ms.openlocfilehash: 055151d4b3e3aba6be9b9b03ac9abffc6eb7b734
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401614"
---
# <a name="how-to-get-the-collection-of-files-in-a-directory-in-visual-basic"></a>Gewusst wie: Abrufen einer Auflistung der Dateien in einem Verzeichnis in Visual Basic

Die Überladungen der <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=nameWithType>-Methode geben eine schreibgeschützte Sammlung an Zeichenfolgen zurück, die die Namen der Dateien innerhalb eines Verzeichnisses darstellen:  
  
- Verwenden Sie die <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29>-Überladung für eine einfache Dateisuche in einem angegebenen Verzeichnis, ohne Unterverzeichnisse zu durchsuchen.  
  
- Verwenden Sie die <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])>-Überladung, um zusätzliche Optionen für Ihre Suche anzugeben. Sie können die `wildCards`-Parameter verwenden, um ein Suchmuster anzugeben. Legen Sie zum Einschließen der Unterverzeichnisse in die Suche den Parameter `searchType` auf <xref:Microsoft.VisualBasic.FileIO.SearchOption.SearchAllSubDirectories?displayProperty=nameWithType> fest.  
  
 Es wird eine leere Sammlung zurückgegeben, wenn keine Dateien dem angegebenen Muster entsprechen.  
  
### <a name="to-list-files-in-a-directory"></a>So listen Sie Dateien in einem Verzeichnis auf  
  
- Verwenden Sie eine der <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=nameWithType>-Methodenüberladungen, geben Sie den Namen und Pfad des zu durchsuchenden Verzeichnisses im Parameter `directory` an. Im folgenden Beispiel werden alle Dateien im Verzeichnis zurückgegeben und `ListBox1` hinzugefügt.  
  
     [!code-vb[VbVbcnMyFileSystem#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#32)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).  
  
- Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).  
  
- `directory` ist nicht vorhanden (<xref:System.IO.DirectoryNotFoundException>).  
  
- `directory` verweist auf eine vorhandene Datei (<xref:System.IO.IOException>).  
  
- Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).  
  
- Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).  
  
- Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).  
  
- Der Benutzer verfügt nicht über die erforderlichen Berechtigungen (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A>
- [Gewusst wie: Suchen nach Dateien mit einem bestimmten Muster](how-to-find-files-with-a-specific-pattern.md)
- [Gewusst wie: Suchen nach Unterverzeichnissen mit einem bestimmten Muster](how-to-find-subdirectories-with-a-specific-pattern.md)
