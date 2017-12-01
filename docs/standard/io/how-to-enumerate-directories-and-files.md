---
title: 'Gewusst wie: Auflisten von Verzeichnissen und Dateien'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: caf9bdec017a5466269ff7fe97be4d0243035b4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-directories-and-files"></a>Gewusst wie: Auflisten von Verzeichnissen und Dateien
Auflisten von Verzeichnissen und Dateien mithilfe von Methoden, die eine aufzählbare Auflistung von Zeichenfolgen in ihren Namen zurückgeben. Sie können auch Methoden, mit denen eine aufzählbare Auflistung von <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, oder <xref:System.IO.FileSystemInfo> Objekte. Aufzählbare Auflistungen ermöglichen eine bessere Leistung als Arrays, bei der Arbeit mit großen Auflistungen von Verzeichnissen und Dateien.  
  
 Sie können auch aufzählbare Auflistungen, die von diesen Methoden abgerufen, geben Sie die <xref:System.Collections.Generic.IEnumerable%601> -Parameter für Konstruktoren Auflistung Klassen wie der <xref:System.Collections.Generic.List%601> Klasse.  
  
 Wenn Sie nur die Namen von Verzeichnissen oder Dateien abrufen möchten, verwenden Sie die Enumerationsmethoden von der <xref:System.IO.Directory> Klasse. Wenn Sie andere Eigenschaften von Verzeichnissen oder Dateien abrufen möchten, verwenden Sie die <xref:System.IO.DirectoryInfo> und <xref:System.IO.FileSystemInfo> Klassen.  
  
 Die folgende Tabelle enthält eine Anleitung für die Methoden, die aufzählbare Auflistungen zurückgeben.  
  
|Auflisten|Aufzählbare Auflistung zurückzugebenden|Zu verwendende Replikationsmethode|  
|------------------|-------------------------------------|-------------------|  
|Verzeichnisse|Verzeichnisnamen|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||Verzeichnisinformationen (<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|Dateien|Dateinamen|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||Dateiinformationen (<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Systeminformationen|Dateisystemeinträgen|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||Informationen zum Dateisystem (<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 Obwohl Sie sofort alle Dateien in den Unterverzeichnissen des übergeordneten Verzeichnisses mit auflisten können die <xref:System.IO.SearchOption.AllDirectories> Option gebotenen Suchen der <xref:System.IO.SearchOption> -Enumeration, die vor nicht autorisiertem Zugriffsausnahmen (<xref:System.UnauthorizedAccessException>) kann dazu führen, dass die Enumeration unvollständig sein. Wenn diese Ausnahmen möglich sind, können Sie sie abfangen und fortsetzen, indem zuerst Auflisten von Verzeichnissen und Dateien dann aufzählt.  
  
### <a name="to-enumerate-directory-names"></a>Verzeichnisnamen auflisten  
  
-   Verwenden der <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> Methode, um eine Liste von Verzeichnisnamen in einem angegebenen Pfad der obersten Ebene abzurufen.  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a>Dateinamen in einem Verzeichnis und die Unterverzeichnisse aufgelistet werden.  
  
-   Verwenden der <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> Methode, um ein Verzeichnis und (optional) der Unterverzeichnisse durchsucht, und um eine Liste von Dateinamen abzurufen, die einem angegebenen Suchmuster entsprechen.  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a>Zum Aufzählen einer Auflistung von DirectoryInfo-Objekte  
  
-   Verwenden der <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> Methode, um eine Auflistung von Verzeichnissen der obersten Ebene abzurufen.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a>Zum Aufzählen einer Auflistung von FileInfo-Objekten in allen Verzeichnissen  
  
-   Verwenden der <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> Methode zum Abrufen einer Auflistung von Dateien, die in allen Verzeichnissen einem angegebenen Suchmuster entsprechen. In diesem Beispiel wird zuerst listet Verzeichnisse der obersten Ebene zum Abfangen von Ausnahmen nicht autorisierten Zugriff auf und zählt dann die Dateien.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
