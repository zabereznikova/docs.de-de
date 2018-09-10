---
title: 'Gewusst wie: Auflisten von Verzeichnissen und Dateien'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3de83395df9e8c89a92e85b96ddd15e9f0be6ad5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44207693"
---
# <a name="how-to-enumerate-directories-and-files"></a>Gewusst wie: Auflisten von Verzeichnissen und Dateien
Sie können Verzeichnisse und Dateien mithilfe von Methoden aufzählen, die eine aufzählbare Sammlung von Zeichenfolgen ihrer Namen zurückgeben. Sie können auch Methoden verwenden, die eine aufzählbare Sammlung von <xref:System.IO.DirectoryInfo>-, <xref:System.IO.FileInfo>- oder <xref:System.IO.FileSystemInfo>-Objekten zurückgeben. Aufzählbare Sammlungen bieten bei der Arbeit mit großen Sammlungen von Verzeichnissen und Dateien eine bessere Leistung als Arrays.  
  
 Sie können mit von diesen Methoden abgerufenen aufzählbaren Sammlungen auch den <xref:System.Collections.Generic.IEnumerable%601>-Parameter für Konstruktoren von Sammlungsklassen wie der <xref:System.Collections.Generic.List%601>-Klasse angeben.  
  
 Wenn Sie nur die Namen von Verzeichnissen oder Dateien abrufen möchten, verwenden Sie die Enumerationsmethoden der <xref:System.IO.Directory>-Klasse. Wenn Sie andere Eigenschaften von Verzeichnissen oder Dateien abrufen möchten, verwenden Sie die <xref:System.IO.DirectoryInfo>- und <xref:System.IO.FileSystemInfo>-Klasse.  
  
 Die folgende Tabelle enthält eine Anleitung für die Methoden, die aufzählbare Sammlungen zurückgeben.  
  
|Aufzuzählendes|Zurückzugebende aufzählbare Sammlung|Zu verwendende Methode|  
|------------------|-------------------------------------|-------------------|  
|Verzeichnisse|Verzeichnisnamen|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||Verzeichnisinformationen (<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|Dateien|Dateinamen|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||Dateiinformationen (<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Dateisysteminformationen|Dateisystemeinträge|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||Dateisysteminformationen (<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 Sie können zwar mithilfe der <xref:System.IO.SearchOption.AllDirectories>-Suchoption der <xref:System.IO.SearchOption>-Enumeration sofort alle Dateien in den Unterverzeichnissen eines übergeordneten Verzeichnisses aufzählen, doch Ausnahmen in Form nicht autorisierten Zugriffs (<xref:System.UnauthorizedAccessException>) können dazu führen, dass die Enumeration unvollständig ist. Wenn diese Ausnahmen möglich sind, können Sie sie abfangen und fortfahren, indem Sie zuerst Verzeichnisse und dann Dateien aufzählen.  
  
### <a name="to-enumerate-directory-names"></a>So zählen Sie Verzeichnisnamen auf  
  
-   Rufen Sie mit der <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType>-Methode eine Liste von Verzeichnisnamen der obersten Ebene in einem angegebenen Pfad ab.  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a>So zählen Sie Dateinamen in einem Verzeichnis und Unterverzeichnissen auf  
  
-   Verwenden Sie die <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType>-Methode, um ein Verzeichnis und (optional) seine Unterverzeichnisse zu durchsuchen, und um eine Liste von Dateinamen abzurufen, die einem angegebenen Suchmuster entsprechen.  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a>So zählen Sie eine Sammlung von DirectoryInfo-Objekten auf  
  
-   Rufen Sie mit der <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>-Methode eine Sammlung von Verzeichnissen der obersten Ebene ab.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a>So zählen Sie eine Sammlung von FileInfo-Objekten in allen Verzeichnissen auf  
  
-   Rufen Sie mit der <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>-Methode in allen Verzeichnissen eine Sammlung von Dateien ab, die einem angegebenen Suchmuster entsprechen. In diesem Beispiel werden zuerst die Verzeichnisse der obersten Ebene aufgezählt, um mögliche Ausnahmen in Form nicht autorisierten Zugriffs abzufangen, und dann die Dateien.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
