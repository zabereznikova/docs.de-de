---
title: "Gewusst wie: Auflisten von Verzeichnissen und Dateien | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "E/A [.NET Framework], Auflisten von Verzeichnissen und Dateien"
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: 18
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Auflisten von Verzeichnissen und Dateien
Sie können Verzeichnisse und Dateien auflisten, mit Methoden, denen eine aufzählbare Auflistung der Zeichenfolgen ihrer Namen zurückgegeben wird.  Sie können auch Methoden verwenden, bei denen eine aufzählbare Auflistung von folgenden Objekten zurückgegeben wird: <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> oder <xref:System.IO.FileSystemInfo>.  Aufzählbare Auflistungen bieten eine bessere Leistung als Arrays, wenn Sie mit großen Auflistungen Verzeichnissen und Dateien arbeiten.  
  
 Sie können auch aufzählbare Auflistungen verwenden, die von diesen Methoden abgerufen werden, um den <xref:System.Collections.Generic.IEnumerable%601>\-Parameter für Konstruktoren von Auflistungsklassen bereitzustellen, z. B. die <xref:System.Collections.Generic.List%601>\-Klasse.  
  
 Wenn Sie nur die Namen von Verzeichnissen oder Dateien abrufen möchten, verwenden Sie die Enumerationsmethoden der <xref:System.IO.Directory>\-Klasse.  Wenn Sie andere Eigenschaften von Verzeichnissen oder Dateien abrufen möchten, verwenden Sie die <xref:System.IO.DirectoryInfo>\-Klasse und die <xref:System.IO.FileSystemInfo>\-Klasse.  
  
 Die folgende Tabelle enthält Informationen zu den Methoden, von denen aufzählbare Auflistungen zurückgegeben werden.  
  
|Aufzulistendes|Aufzählbare Auflistung, die zurückgegeben werden soll|Zu verwendende Methode|  
|--------------------|-----------------------------------------------------------|----------------------------|  
|Verzeichnisse|Verzeichnisnamen|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=fullName>|  
||Verzeichnisinformationen \(<xref:System.IO.DirectoryInfo>\)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=fullName>|  
|Dateien|Dateinamen|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=fullName>|  
||Dateiinformationen \(<xref:System.IO.FileInfo>\)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=fullName>|  
|Dateisysteminformationen|Dateisystemeinträge|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=fullName>|  
||Dateisysteminformationen \(<xref:System.IO.FileSystemInfo>\)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=fullName>|  
  
 Obwohl Sie alle Dateien in den Unterverzeichnissen eines übergeordneten Verzeichnisses sofort auflisten können, indem die <xref:System.IO.SearchOption> Suchoption verwenden, die von der <xref:System.IO.SearchOption>\-Enumeration bereitgestellt wird, werden möglicherweise aufgrund nicht autorisierter Zugriffsausnahmen \(<xref:System.UnauthorizedAccessException>\) die Enumeration, unter Umständen unvollständig sein.  Wenn diese Ausnahmen möglich sind, können Sie sie erfassen und fortsetzen, indem zuerst Verzeichnisse und anschließend Dateien aufgelistet werden.  
  
### So listen Sie Verzeichnisnamen auf  
  
-   Verwenden Sie die <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=fullName>\-Methode, um eine Liste der Verzeichnisnamen der obersten Ebene in einem angegebenen Pfad abzurufen.  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### So Dateinamen in einem Verzeichnis und in den Unterverzeichnissen auflisten  
  
-   Verwenden Sie die <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=fullName>\-Methode, um ein Verzeichnis und \(optional\) seine Unterverzeichnisse zu suchen, und eine Liste von Dateinamen abzurufen, die einem angegebenen Suchmuster entsprechen.  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### So listen Sie eine Auflistung von DirectoryInfo\-Objekten auf  
  
-   Verwenden Sie die <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=fullName>\-Methode, um eine Auflistung von Verzeichnissen der obersten Ebene abzurufen.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### So listen Sie eine Auflistung von FileInfo\-Objekten in allen Verzeichnissen auf  
  
-   Verwenden Sie die <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=fullName>\-Methode, um eine Auflistung von Dateien abzurufen, die in allen Verzeichnissen einem angegebenen Suchmuster entsprechen.  In diesem Beispiel werden zuerst die Verzeichnisse der obersten Ebene aufgelistet, um mögliche nicht autorisierte Zugriffsausnahmen zu erfassen, und anschließend werden die Dateien aufgelistet.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## Siehe auch  
 [Datei\- und Stream\-E\/A](../../../docs/standard/io/index.md)