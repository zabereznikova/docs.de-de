---
title: 'Gewusst wie: Komprimieren und Extrahieren von Dateien'
ms.date: 06/06/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 669936d15cfe1ea125ed36ffdfcfd093b6aacbe1
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45687633"
---
# <a name="how-to-compress-and-extract-files"></a>Gewusst wie: Komprimieren und Extrahieren von Dateien

Der <xref:System.IO.Compression>-Namespace enthält die folgenden Typen zum Komprimieren und Dekomprimieren von Dateien und Streams. Sie können diese Typen auch verwenden, um den Inhalt einer komprimierten Datei zu lesen und zu ändern:

- <xref:System.IO.Compression.ZipFile>

- <xref:System.IO.Compression.ZipArchive>

- <xref:System.IO.Compression.ZipArchiveEntry>

- <xref:System.IO.Compression.DeflateStream>

- <xref:System.IO.Compression.GZipStream>

Die folgenden Beispiele zeigen einige der Funktionen, die Sie beim Arbeiten mit komprimierten Dateien ausführen können.

## <a name="example-1---create-and-extract-a-zip-file"></a>Beispiel 1: Erstellen und Extrahieren einer ZIP-Datei

Das folgende Beispiel zeigt, wie Sie mithilfe der <xref:System.IO.Compression.ZipFile>-Klasse eine komprimierte Datei mit der Erweiterung „ZIP“ erstellen und extrahieren. Das Beispiel komprimiert den Inhalt eines Ordners in eine neue ZIP-Datei und extrahiert diese dann in einen neuen Ordner. Um die <xref:System.IO.Compression.ZipFile>-Klasse zu verwenden, müssen Sie auf die `System.IO.Compression.FileSystem`-Assembly in Ihrem Projekt verweisen.

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2---extract-specific-file-extensions"></a>Beispiel 2: Extrahieren bestimmter Dateierweiterungen

Das nächste Beispiel zeigt, wie Sie den Inhalt einer vorhandenen ZIP-Datei durchlaufen und Dateien mit der Erweiterung „TXT“ extrahieren. Es verwendet die <xref:System.IO.Compression.ZipArchive>-Klasse, um auf eine vorhandene ZIP-Datei zuzugreifen, und die <xref:System.IO.Compression.ZipArchiveEntry>-Klasse, um die einzelnen Einträge in der komprimierten Datei zu untersuchen. Es verwendet eine Erweiterungsmethode (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) für das <xref:System.IO.Compression.ZipArchiveEntry>-Objekt. Die Erweiterungsmethode ist in der <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>-Klasse verfügbar. Um die <xref:System.IO.Compression.ZipFileExtensions>-Klasse zu verwenden, müssen Sie auf die `System.IO.Compression.FileSystem`-Assembly in Ihrem Projekt verweisen.

> [!IMPORTANT]
> Beim Extrahieren von Dateien müssen Sie auf schädliche Dateipfade achten, die aus dem Verzeichnis weisen können, in das Sie extrahieren möchten. Dies wird als Path Traversal-Angriff bezeichnet.

Das folgende Beispiel zeigt die Überprüfung auf schädliche Dateipfade und bietet eine sichere Möglichkeit zum Extrahieren:

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3---add-a-new-file-to-an-existing-zip-file"></a>Beispiel 3: Hinzufügen einer neuen Datei zu einer vorhandenen ZIP-Datei

Im folgenden Beispiel wird die <xref:System.IO.Compression.ZipArchive>-Klasse verwendet, um auf eine vorhandene ZIP-Datei zuzugreifen, und der komprimierten Datei eine neue Datei hinzugefügt. Die neue Datei wird komprimiert, wenn Sie sie zur vorhandenen ZIP-Datei hinzufügen.

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4---compress-and-decompress-a-directory-of-gz-files"></a>Beispiel 4: Komprimieren und Dekomprimieren eines Verzeichnisses von GZ-Dateien

Sie können auch die Klassen <xref:System.IO.Compression.GZipStream> und <xref:System.IO.Compression.DeflateStream> verwenden, um Daten zu komprimieren und zu dekomprimieren. Der Komprimierungsalgorithmus ist der gleiche. Komprimierte <xref:System.IO.Compression.GZipStream>-Objekte, die in eine Datei mit der Erweiterung „GZ“ geschrieben werden, können mit den von <xref:System.IO.Compression.GZipStream> bereitgestellten Methoden sowie mit vielen häufig verwendeten Tools dekomprimiert werden. Das folgende Beispiel zeigt, wie Sie ein Dateiverzeichnis mithilfe der <xref:System.IO.Compression.GZipStream>-Klasse komprimieren und dekomprimieren:

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a>Siehe auch

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
