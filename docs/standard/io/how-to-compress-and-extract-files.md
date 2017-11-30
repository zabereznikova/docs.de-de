---
title: 'Gewusst wie: Komprimieren und Extrahieren von Dateien'
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
helpviewer_keywords:
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
caps.latest.revision: "19"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 22a95ce18b602d4e329499c5d36557213e08a8b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-compress-and-extract-files"></a>Gewusst wie: Komprimieren und Extrahieren von Dateien
Die <xref:System.IO.Compression> -Namespace enthält die folgenden Typen zum Komprimieren und Dekomprimieren von Dateien und Streams. Sie können auch diese Typen verwenden, lesen und ändern Sie den Inhalt einer komprimierten Datei:  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 Die folgenden Beispiele zeigen einige der Funktionen, die Sie ausführen können, bei der Arbeit mit komprimierten Dateien.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird gezeigt, wie zum Erstellen und extrahieren die komprimierte Datei mit der Erweiterung ZIP-Datei mithilfe der <xref:System.IO.Compression.ZipFile> Klasse. Der Inhalt eines Ordners in eine neue ZIP-Datei komprimiert und extrahiert dann Inhalt an einen neuen Ordner. Verwenden der <xref:System.IO.Compression.ZipFile> -Klasse, die Sie verweisen müssen die `System.IO.Compression.FileSystem` Assembly im Projekt.  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## <a name="example"></a>Beispiel  
 Im nächste Beispiel veranschaulicht die Iteration durch den Inhalt einer vorhandenen ZIP-Datei, und Extrahieren von Dateien mit der Erweiterung ".txt". Er verwendet die <xref:System.IO.Compression.ZipArchive> Klasse, um eine vorhandene ZIP-Datei zugreifen und die <xref:System.IO.Compression.ZipArchiveEntry> Klasse, um die einzelnen Einträge in der komprimierten Datei zu überprüfen. Er verwendet eine Erweiterungsmethode (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) für die <xref:System.IO.Compression.ZipArchiveEntry> Objekt. Die Erweiterungsmethode steht in der <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> Klasse. Verwenden der <xref:System.IO.Compression.ZipFileExtensions> -Klasse, die Sie verweisen müssen die `System.IO.Compression.FileSystem` Assembly im Projekt.  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## <a name="example"></a>Beispiel  
 Im nächste Beispiel wird die <xref:System.IO.Compression.ZipArchive> -Klasse für den Zugriff auf eine vorhandene ZIP-Datei und fügt eine neue Datei zur komprimierten Datei. Die neue Datei ruft komprimiert, wenn Sie ihn an die vorhandene ZIP-Datei hinzufügen.  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## <a name="example"></a>Beispiel  
 Sie können auch die <xref:System.IO.Compression.GZipStream> und <xref:System.IO.Compression.DeflateStream> Klassen zum Komprimieren und Dekomprimieren von Daten. Sie verwenden denselben Komprimierungsalgorithmus. Komprimierte <xref:System.IO.Compression.GZipStream> Objekte, die in eine Datei geschrieben werden, mit der Erweiterung der .gz können viele häufig verwendete Tools neben den bereitgestellten Methoden mit dekomprimiert werden <xref:System.IO.Compression.GZipStream>. In diesem Beispiel wird gezeigt, wie zum Komprimieren und Dekomprimieren von Dateien in einem Verzeichnis mithilfe der <xref:System.IO.Compression.GZipStream> Klasse.  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO.Compression.ZipArchive>  
 <xref:System.IO.Compression.ZipFile>  
 <xref:System.IO.Compression.ZipArchiveEntry>  
 <xref:System.IO.Compression.DeflateStream>  
 <xref:System.IO.Compression.GZipStream>  
 [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
