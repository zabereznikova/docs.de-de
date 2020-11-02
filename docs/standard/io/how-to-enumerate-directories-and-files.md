---
title: 'Vorgehensweise: Auflisten von Verzeichnissen und Dateien'
description: Erfahren Sie, wie Sie in .NET Verzeichnisse und Dateien mithilfe von aufzählbaren Sammlungen auflisten, die eine bessere Leistung als Arrays bieten können.
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
ms.openlocfilehash: 7a757fc97fd934f02592264c3a495c3efc435fd5
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93187891"
---
# <a name="how-to-enumerate-directories-and-files"></a>Vorgehensweise: Auflisten von Verzeichnissen und Dateien
Aufzählbare Sammlungen bieten bei der Arbeit mit großen Sammlungen von Verzeichnissen und Dateien eine bessere Leistung als Arrays. Verwenden Sie zum Auflisten von Verzeichnissen und Dateien Methoden, die eine aufzählbare Collection von Verzeichnis- oder Dateinamen zurückgeben, oder ihre <xref:System.IO.DirectoryInfo>-, <xref:System.IO.FileInfo>- oder <xref:System.IO.FileSystemInfo>-Objekte.  
  
Wenn Sie nur die Namen von Verzeichnissen oder Dateien suchen und zurückgegeben möchten, verwenden Sie die Enumerationsmethoden der <xref:System.IO.Directory>-Klasse. Wenn Sie andere Eigenschaften von Verzeichnissen oder Dateien abrufen möchten, verwenden Sie die <xref:System.IO.DirectoryInfo>- und <xref:System.IO.FileSystemInfo>-Klasse.  
  
Sie können die aufzählbaren Auflistungen dieser Methoden als <xref:System.Collections.Generic.IEnumerable%601>-Parameter für Konstruktoren von Auflistungsklassen wie <xref:System.Collections.Generic.List%601> verwenden.  
  
In der folgenden Tabelle werden die Methoden zusammengefasst, die aufzählbare Auflistungen von Dateien und Verzeichnissen zurückgeben:  
  
|Zum Abrufen von|Zu verwendende Methode|  
|------------------|-------------------------------------|-------------------|  
|Verzeichnisnamen|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|Verzeichnisinformationen (<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|Dateinamen|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Dateiinformationen (<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Namen von Dateisystemeinträgen|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
|Informationen zu Dateisystemeinträgen (<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
|Verzeichnis- und Dateinamen |<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  

> [!NOTE]
> Obwohl Sie alle Dateien in den Unterverzeichnissen eines übergeordneten Verzeichnisses mithilfe der <xref:System.IO.SearchOption.AllDirectories>-Option der optionalen <xref:System.IO.SearchOption>-Enumeration sofort aufzählen können, können die Enumerationen aufgrund von <xref:System.UnauthorizedAccessException>-Fehlern unvollständig sein. Sie können diese Ausnahmen erfassen, indem Sie zuerst die Verzeichnisse und dann die Dateien aufzählen.  
  
## <a name="examples-use-the-directory-class"></a>Beispiele: Verwenden der Directory-Klasse  
  
Im folgenden Beispiel wird die <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType>-Methode verwendet, um eine Liste der Verzeichnisnamen im angegebenen Pfad abzurufen.  

[!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
[!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  

Im folgenden Beispiel wird die <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType>-Methode verwendet, um alle Dateinamen in einem Verzeichnis und den Unterverzeichnissen aufzuzählen, die einem bestimmten Muster entsprechen. Anschließend wird jede Zeile jeder Datei gelesen, und die Zeilen, die die angegebene Zeichenfolge enthalten, werden samt Dateinamen und Pfaden angezeigt.

[!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
[!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
## <a name="examples-use-the-directoryinfo-class"></a>Beispiele: Verwenden der DirectoryInfo-Klasse  
  
Im folgenden Beispiel wird die <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>-Methode zum Auflisten einer Collection von Verzeichnissen verwendet, deren <xref:System.IO.FileSystemInfo.CreationTimeUtc>-Eigenschaft einen Zeitwert vor dem Wert von <xref:System.DateTime> enthält.  

[!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs)]
[!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb)]  
  
Im folgenden Beispiel wird die <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>-Methode zum Auflisten aller Dateien verwendet, deren <xref:System.IO.FileInfo.Length>-Wert über 10 MB liegt. In diesem Beispiel werden zunächst die obersten Verzeichnisse aufgezählt, um mögliche Ausnahmen in Form nicht autorisierten Zugriffs abzufangen, und dann die Dateien.  

[!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
[!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Datei- und Stream-E/A](index.md)
