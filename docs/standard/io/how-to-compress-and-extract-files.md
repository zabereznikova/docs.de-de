---
title: 'Vorgehensweise: Komprimieren und Extrahieren von Dateien'
description: Komprimieren und extrahieren Sie Dateien mit System.IO.Compression. Dieser Artikel enthält Verwendungsbeispiele für ZipFile, ZipArchive, ZipArchiveEntry, DeflateStream und GZipStream.
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
ms.openlocfilehash: c13f464432aa6f67136d3a844bdeda256e7ab9b6
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769235"
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="67d34-104">Vorgehensweise: Komprimieren und Extrahieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="67d34-104">How to: Compress and extract files</span></span>

<span data-ttu-id="67d34-105">Der <xref:System.IO.Compression>-Namespace enthält die folgenden Typen zum Komprimieren und Dekomprimieren von Dateien und Streams.</span><span class="sxs-lookup"><span data-stu-id="67d34-105">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="67d34-106">Sie können diese Typen auch verwenden, um den Inhalt einer komprimierten Datei zu lesen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="67d34-106">You can also use these types to read and modify the contents of a compressed file.</span></span>

- <xref:System.IO.Compression.ZipFile>
- <xref:System.IO.Compression.ZipArchive>
- <xref:System.IO.Compression.ZipArchiveEntry>
- <xref:System.IO.Compression.DeflateStream>
- <xref:System.IO.Compression.GZipStream>

<span data-ttu-id="67d34-107">Anhand der folgenden Beispiele werden einige der Vorgänge erläutert, die Sie mit komprimierten Dateien ausführen können.</span><span class="sxs-lookup"><span data-stu-id="67d34-107">The following examples show some of the operations you can perform with compressed files.</span></span> <span data-ttu-id="67d34-108">Für diese Beispiele müssen Ihrem Projekt die folgenden NuGet-Pakete hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="67d34-108">These examples require the following NuGet packages to be added to your project:</span></span>

- [<span data-ttu-id="67d34-109">System.IO.Compression</span><span class="sxs-lookup"><span data-stu-id="67d34-109">System.IO.Compression</span></span>](https://www.nuget.org/packages/System.IO.Compression)
- [<span data-ttu-id="67d34-110">System.IO.Compression.ZipFile</span><span class="sxs-lookup"><span data-stu-id="67d34-110">System.IO.Compression.ZipFile</span></span>](https://www.nuget.org/packages/System.IO.Compression.ZipFile)

<span data-ttu-id="67d34-111">Wenn Sie .NET Framework verwenden, fügen Sie Ihrem Projekt Verweise auf diese zwei Bibliotheken hinzu:</span><span class="sxs-lookup"><span data-stu-id="67d34-111">If you're using .NET Framework, add references to these two libraries to your project:</span></span>

- `System.IO.Compression`
- `System.IO.Compression.FileSystem`

## <a name="example-1-create-and-extract-a-zip-file"></a><span data-ttu-id="67d34-112">Beispiel 1: Erstellen und Extrahieren einer ZIP-Datei</span><span class="sxs-lookup"><span data-stu-id="67d34-112">Example 1: Create and extract a .zip file</span></span>

<span data-ttu-id="67d34-113">Das folgende Beispiel zeigt, wie Sie mithilfe der <xref:System.IO.Compression.ZipFile>-Klasse eine komprimierte *ZIP*-Datei erstellen und extrahieren können.</span><span class="sxs-lookup"><span data-stu-id="67d34-113">The following example shows how to create and extract a compressed *.zip* file by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="67d34-114">In dem Beispiel wird der Inhalt eines Ordners in eine neue *ZIP*-Datei komprimiert, die anschließend in einen neuen Ordner extrahiert wird.</span><span class="sxs-lookup"><span data-stu-id="67d34-114">The example compresses the contents of a folder into a new *.zip* file, and then extracts the zip to a new folder.</span></span>

<span data-ttu-id="67d34-115">Wenn Sie das Beispiel ausführen möchten, erstellen Sie in Ihrem Programmordner einen Ordner für den *Start*, und füllen Sie diesen mit Dateien auf, die gezippt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="67d34-115">To run the sample, create a *start* folder in your program folder and populate it with files to zip.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2-extract-specific-file-extensions"></a><span data-ttu-id="67d34-116">Beispiel 2: Extrahieren bestimmter Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="67d34-116">Example 2: Extract specific file extensions</span></span>

<span data-ttu-id="67d34-117">Im nächsten Beispiel wird der Inhalt einer vorhandenen *ZIP*-Datei durchlaufen, und Dateien mit der Erweiterung *.txt* werden extrahiert.</span><span class="sxs-lookup"><span data-stu-id="67d34-117">The next example iterates through the contents of an existing *.zip* file and extracts files that have a *.txt* extension.</span></span> <span data-ttu-id="67d34-118">Dabei wird die Klasse <xref:System.IO.Compression.ZipArchive> verwendet, um auf die Zip-Datei zuzugreifen, und mithilfe der Klasse <xref:System.IO.Compression.ZipArchiveEntry> werden die einzelnen Einträge untersucht.</span><span class="sxs-lookup"><span data-stu-id="67d34-118">It uses the <xref:System.IO.Compression.ZipArchive> class to access the zip, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries.</span></span> <span data-ttu-id="67d34-119">Die Erweiterungsmethode <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> für das <xref:System.IO.Compression.ZipArchiveEntry>-Objekt ist in der Klasse <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> verfügbar.</span><span class="sxs-lookup"><span data-stu-id="67d34-119">The extension method <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> for the <xref:System.IO.Compression.ZipArchiveEntry> object is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span>

<span data-ttu-id="67d34-120">Wenn Sie das Beispiel ausführen möchten, platzieren Sie die *ZIP*-Datei mit dem Namen *result.zip* in Ihrem Programmordner.</span><span class="sxs-lookup"><span data-stu-id="67d34-120">To run the sample, place a *.zip* file called *result.zip* in your program folder.</span></span> <span data-ttu-id="67d34-121">Geben Sie einen Ordnernamen an, in den die Datei extrahiert werden soll, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="67d34-121">When prompted, provide a folder name to extract to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67d34-122">Beim Entzippen von Dateien müssen Sie auf schädliche Dateipfade achten, die aus dem Verzeichnis weisen können, in das Sie extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="67d34-122">When unzipping files, you must look for malicious file paths, which can escape out of the directory you unzip into.</span></span> <span data-ttu-id="67d34-123">Dies wird als Path Traversal-Angriff bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="67d34-123">This is known as a path traversal attack.</span></span> <span data-ttu-id="67d34-124">Im folgenden Beispiel wird gezeigt, wie Sie eine Überprüfung auf schädliche Dateipfade durchführen und Dateien sicher entzippen können.</span><span class="sxs-lookup"><span data-stu-id="67d34-124">The following example demonstrates how to check for malicious file paths and provides a safe way to unzip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3-add-a-file-to-an-existing-zip"></a><span data-ttu-id="67d34-125">Beispiel 3: Hinzufügen einer Datei zu einer bestehenden ZIP-Datei</span><span class="sxs-lookup"><span data-stu-id="67d34-125">Example 3: Add a file to an existing zip</span></span>

<span data-ttu-id="67d34-126">Im folgenden Beispiel wird die Klasse <xref:System.IO.Compression.ZipArchive> verwendet, um auf eine vorhandene *ZIP*-Datei zuzugreifen, der anschließend eine Datei hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="67d34-126">The following example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing *.zip* file, and adds a file to it.</span></span> <span data-ttu-id="67d34-127">Die neue Datei wird komprimiert, wenn Sie sie zur vorhandenen ZIP-Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="67d34-127">The new file gets compressed when you add it to the existing zip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4-compress-and-decompress-gz-files"></a><span data-ttu-id="67d34-128">Beispiel 4: Komprimieren und Dekomprimieren von GZ-Dateien</span><span class="sxs-lookup"><span data-stu-id="67d34-128">Example 4: Compress and decompress .gz files</span></span>

<span data-ttu-id="67d34-129">Sie können auch die Klassen <xref:System.IO.Compression.GZipStream> und <xref:System.IO.Compression.DeflateStream> verwenden, um Daten zu komprimieren und zu dekomprimieren.</span><span class="sxs-lookup"><span data-stu-id="67d34-129">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="67d34-130">Der Komprimierungsalgorithmus ist der gleiche.</span><span class="sxs-lookup"><span data-stu-id="67d34-130">They use the same compression algorithm.</span></span> <span data-ttu-id="67d34-131">Es gibt viele beliebte Tools, die Sie verwenden können, um <xref:System.IO.Compression.GZipStream>-Objekte zu dekomprimieren, die in eine *GZ*-Datei geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="67d34-131">You can decompress <xref:System.IO.Compression.GZipStream> objects that are written to a *.gz* file by using many common tools.</span></span> <span data-ttu-id="67d34-132">Das folgende Beispiel zeigt, wie Sie ein Dateiverzeichnis mithilfe der <xref:System.IO.Compression.GZipStream>-Klasse komprimieren und dekomprimieren:</span><span class="sxs-lookup"><span data-stu-id="67d34-132">The following example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class:</span></span>

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a><span data-ttu-id="67d34-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67d34-133">See also</span></span>

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [<span data-ttu-id="67d34-134">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="67d34-134">File and stream I/O</span></span>](index.md)
