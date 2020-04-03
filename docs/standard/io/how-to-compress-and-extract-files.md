---
title: 'Vorgehensweise: Komprimieren und Extrahieren von Dateien'
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
ms.openlocfilehash: 10f990401830bc5f77176f4e586f15f7dd75ff14
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80248016"
---
# <a name="how-to-compress-and-extract-files"></a>Vorgehensweise: Komprimieren und Extrahieren von Dateien

Der <xref:System.IO.Compression>-Namespace enthält die folgenden Typen zum Komprimieren und Dekomprimieren von Dateien und Streams. Sie können diese Typen auch verwenden, um den Inhalt einer komprimierten Datei zu lesen und zu ändern.

- <xref:System.IO.Compression.ZipFile>
- <xref:System.IO.Compression.ZipArchive>
- <xref:System.IO.Compression.ZipArchiveEntry>
- <xref:System.IO.Compression.DeflateStream>
- <xref:System.IO.Compression.GZipStream>

Anhand der folgenden Beispiele werden einige der Vorgänge erläutert, die Sie mit komprimierten Dateien ausführen können. Für diese Beispiele müssen Ihrem Projekt die folgenden NuGet-Pakete hinzugefügt werden:

- [System.IO.Compression](https://www.nuget.org/packages/System.IO.Compression)
- [System.IO.Compression.ZipFile](https://www.nuget.org/packages/System.IO.Compression.ZipFile)

Wenn Sie .NET Framework verwenden, fügen Sie Ihrem Projekt Verweise auf diese zwei Bibliotheken hinzu:

- `System.IO.Compression`
- `System.IO.Compression.FileSystem`

## <a name="example-1-create-and-extract-a-zip-file"></a>Beispiel 1: Erstellen und Extrahieren einer ZIP-Datei

Das folgende Beispiel zeigt, wie Sie mithilfe der <xref:System.IO.Compression.ZipFile>-Klasse eine komprimierte *ZIP*-Datei erstellen und extrahieren können. In dem Beispiel wird der Inhalt eines Ordners in eine neue *ZIP*-Datei komprimiert, die anschließend in einen neuen Ordner extrahiert wird.

Wenn Sie das Beispiel ausführen möchten, erstellen Sie in Ihrem Programmordner einen Ordner für den *Start*, und füllen Sie diesen mit Dateien auf, die gezippt werden sollen.

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2-extract-specific-file-extensions"></a>Beispiel 2: Extrahieren bestimmter Dateierweiterungen

Im nächsten Beispiel wird der Inhalt einer vorhandenen *ZIP*-Datei durchlaufen, und Dateien mit der Erweiterung *.txt* werden extrahiert. Dabei wird die Klasse <xref:System.IO.Compression.ZipArchive> verwendet, um auf die Zip-Datei zuzugreifen, und mithilfe der Klasse <xref:System.IO.Compression.ZipArchiveEntry> werden die einzelnen Einträge untersucht. Die Erweiterungsmethode <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> für das <xref:System.IO.Compression.ZipArchiveEntry>-Objekt ist in der Klasse <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> verfügbar.

Wenn Sie das Beispiel ausführen möchten, platzieren Sie die *ZIP*-Datei mit dem Namen *result.zip* in Ihrem Programmordner. Geben Sie einen Ordnernamen an, in den die Datei extrahiert werden soll, wenn Sie dazu aufgefordert werden.

> [!IMPORTANT]
> Beim Entzippen von Dateien müssen Sie auf schädliche Dateipfade achten, die aus dem Verzeichnis weisen können, in das Sie extrahieren möchten. Dies wird als Path Traversal-Angriff bezeichnet. Im folgenden Beispiel wird gezeigt, wie Sie eine Überprüfung auf schädliche Dateipfade durchführen und Dateien sicher entzippen können.

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3-add-a-file-to-an-existing-zip"></a>Beispiel 3: Hinzufügen einer Datei zu einer bestehenden ZIP-Datei

Im folgenden Beispiel wird die Klasse <xref:System.IO.Compression.ZipArchive> verwendet, um auf eine vorhandene *ZIP*-Datei zuzugreifen, der anschließend eine Datei hinzugefügt wird. Die neue Datei wird komprimiert, wenn Sie sie zur vorhandenen ZIP-Datei hinzufügen.

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4-compress-and-decompress-gz-files"></a>Beispiel 4: Komprimieren und Dekomprimieren von GZ-Dateien

Sie können auch die Klassen <xref:System.IO.Compression.GZipStream> und <xref:System.IO.Compression.DeflateStream> verwenden, um Daten zu komprimieren und zu dekomprimieren. Der Komprimierungsalgorithmus ist der gleiche. Es gibt viele beliebte Tools, die Sie verwenden können, um <xref:System.IO.Compression.GZipStream>-Objekte zu dekomprimieren, die in eine *GZ*-Datei geschrieben wurden. Das folgende Beispiel zeigt, wie Sie ein Dateiverzeichnis mithilfe der <xref:System.IO.Compression.GZipStream>-Klasse komprimieren und dekomprimieren:

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a>Siehe auch

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
