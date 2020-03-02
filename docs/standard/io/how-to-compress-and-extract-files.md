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
ms.openlocfilehash: 5aa25e265ed6ffb613e9916414c6f2335a4aaf57
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159376"
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="84413-102">Vorgehensweise: Komprimieren und Extrahieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="84413-102">How to: Compress and extract files</span></span>

<span data-ttu-id="84413-103">Der <xref:System.IO.Compression>-Namespace enthält die folgenden Typen zum Komprimieren und Dekomprimieren von Dateien und Streams.</span><span class="sxs-lookup"><span data-stu-id="84413-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="84413-104">Sie können diese Typen auch verwenden, um den Inhalt einer komprimierten Datei zu lesen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="84413-104">You can also use these types to read and modify the contents of a compressed file.</span></span>

- <xref:System.IO.Compression.ZipFile>
- <xref:System.IO.Compression.ZipArchive>
- <xref:System.IO.Compression.ZipArchiveEntry>
- <xref:System.IO.Compression.DeflateStream>
- <xref:System.IO.Compression.GZipStream>

<span data-ttu-id="84413-105">Anhand der folgenden Beispiele werden einige der Vorgänge erläutert, die Sie mit komprimierten Dateien ausführen können.</span><span class="sxs-lookup"><span data-stu-id="84413-105">The following examples show some of the operations you can perform with compressed files.</span></span>

## <a name="example-1-create-and-extract-a-zip-file"></a><span data-ttu-id="84413-106">Beispiel 1: Erstellen und Extrahieren einer ZIP-Datei</span><span class="sxs-lookup"><span data-stu-id="84413-106">Example 1: Create and extract a .zip file</span></span>

<span data-ttu-id="84413-107">Das folgende Beispiel zeigt, wie Sie mithilfe der <xref:System.IO.Compression.ZipFile>-Klasse eine komprimierte *ZIP*-Datei erstellen und extrahieren können.</span><span class="sxs-lookup"><span data-stu-id="84413-107">The following example shows how to create and extract a compressed *.zip* file by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="84413-108">In dem Beispiel wird der Inhalt eines Ordners in eine neue *ZIP*-Datei komprimiert, die anschließend in einen neuen Ordner extrahiert wird.</span><span class="sxs-lookup"><span data-stu-id="84413-108">The example compresses the contents of a folder into a new *.zip* file, and then extracts the zip to a new folder.</span></span>

<span data-ttu-id="84413-109">Wenn Sie das Beispiel ausführen möchten, erstellen Sie in Ihrem Programmordner einen Ordner für den *Start*, und füllen Sie diesen mit Dateien auf, die gezippt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="84413-109">To run the sample, create a *start* folder in your program folder and populate it with files to zip.</span></span>

<span data-ttu-id="84413-110">Wenn der Buildfehler "The name 'ZipFile' does not exist in the current context." (Der Name „ZipFile“ ist im aktuellen Kontext nicht vorhanden.) zurückgegeben wird, fügen Sie dem Projekt einen Verweis auf die `System.IO.Compression.FileSystem`-Assembly hinzu.</span><span class="sxs-lookup"><span data-stu-id="84413-110">If you get the build error "The name 'ZipFile' does not exist in the current context," add a reference to the `System.IO.Compression.FileSystem` assembly to your project.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2-extract-specific-file-extensions"></a><span data-ttu-id="84413-111">Beispiel 2: Extrahieren bestimmter Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="84413-111">Example 2: Extract specific file extensions</span></span>

<span data-ttu-id="84413-112">Im nächsten Beispiel wird der Inhalt einer vorhandenen *ZIP*-Datei durchlaufen, und Dateien mit der Erweiterung *.txt* werden extrahiert.</span><span class="sxs-lookup"><span data-stu-id="84413-112">The next example iterates through the contents of an existing *.zip* file and extracts files that have a *.txt* extension.</span></span> <span data-ttu-id="84413-113">Dabei wird die Klasse <xref:System.IO.Compression.ZipArchive> verwendet, um auf die Zip-Datei zuzugreifen, und mithilfe der Klasse <xref:System.IO.Compression.ZipArchiveEntry> werden die einzelnen Einträge untersucht.</span><span class="sxs-lookup"><span data-stu-id="84413-113">It uses the <xref:System.IO.Compression.ZipArchive> class to access the zip, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries.</span></span> <span data-ttu-id="84413-114">Die Erweiterungsmethode <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> für das <xref:System.IO.Compression.ZipArchiveEntry>-Objekt ist in der Klasse <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> verfügbar.</span><span class="sxs-lookup"><span data-stu-id="84413-114">The extension method <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> for the <xref:System.IO.Compression.ZipArchiveEntry> object is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span>

<span data-ttu-id="84413-115">Wenn Sie das Beispiel ausführen möchten, platzieren Sie die *ZIP*-Datei mit dem Namen *result.zip* in Ihrem Programmordner.</span><span class="sxs-lookup"><span data-stu-id="84413-115">To run the sample, place a *.zip* file called *result.zip* in your program folder.</span></span> <span data-ttu-id="84413-116">Geben Sie einen Ordnernamen an, in den die Datei extrahiert werden soll, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="84413-116">When prompted, provide a folder name to extract to.</span></span>

<span data-ttu-id="84413-117">Wenn der Buildfehler "The name 'ZipFile' does not exist in the current context." (Der Name „ZipFile“ ist im aktuellen Kontext nicht vorhanden.) zurückgegeben wird, fügen Sie dem Projekt einen Verweis auf die `System.IO.Compression.FileSystem`-Assembly hinzu.</span><span class="sxs-lookup"><span data-stu-id="84413-117">If you get the build error "The name 'ZipFile' does not exist in the current context," add a reference to the `System.IO.Compression.FileSystem` assembly to your project.</span></span>

<span data-ttu-id="84413-118">Wenn der Fehler "The type 'ZipArchive' is defined in an assembly that is not referenced." (Der Typ „ZipArchive“ ist in einer Assembly definiert, auf die nicht verwiesen wird.) zurückgegeben wird, fügen Sie dem Projekt einen Verweis auf die `System.IO.Compression`-Assembly hinzu.</span><span class="sxs-lookup"><span data-stu-id="84413-118">If you get the error "The type 'ZipArchive' is defined in an assembly that is not referenced," add a reference to the `System.IO.Compression` assembly to your project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84413-119">Beim Entzippen von Dateien müssen Sie auf schädliche Dateipfade achten, die aus dem Verzeichnis weisen können, in das Sie extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="84413-119">When unzipping files, you must look for malicious file paths, which can escape out of the directory you unzip into.</span></span> <span data-ttu-id="84413-120">Dies wird als Path Traversal-Angriff bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="84413-120">This is known as a path traversal attack.</span></span> <span data-ttu-id="84413-121">Im folgenden Beispiel wird gezeigt, wie Sie eine Überprüfung auf schädliche Dateipfade durchführen und Dateien sicher entzippen können.</span><span class="sxs-lookup"><span data-stu-id="84413-121">The following example demonstrates how to check for malicious file paths and provides a safe way to unzip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3-add-a-file-to-an-existing-zip"></a><span data-ttu-id="84413-122">Beispiel 3: Hinzufügen einer Datei zu einer bestehenden ZIP-Datei</span><span class="sxs-lookup"><span data-stu-id="84413-122">Example 3: Add a file to an existing zip</span></span>

<span data-ttu-id="84413-123">Im folgenden Beispiel wird die Klasse <xref:System.IO.Compression.ZipArchive> verwendet, um auf eine vorhandene *ZIP*-Datei zuzugreifen, der anschließend eine Datei hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="84413-123">The following example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing *.zip* file, and adds a file to it.</span></span> <span data-ttu-id="84413-124">Die neue Datei wird komprimiert, wenn Sie sie zur vorhandenen ZIP-Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="84413-124">The new file gets compressed when you add it to the existing zip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4-compress-and-decompress-gz-files"></a><span data-ttu-id="84413-125">Beispiel 4: Komprimieren und Dekomprimieren von GZ-Dateien</span><span class="sxs-lookup"><span data-stu-id="84413-125">Example 4: Compress and decompress .gz files</span></span>

<span data-ttu-id="84413-126">Sie können auch die Klassen <xref:System.IO.Compression.GZipStream> und <xref:System.IO.Compression.DeflateStream> verwenden, um Daten zu komprimieren und zu dekomprimieren.</span><span class="sxs-lookup"><span data-stu-id="84413-126">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="84413-127">Der Komprimierungsalgorithmus ist der gleiche.</span><span class="sxs-lookup"><span data-stu-id="84413-127">They use the same compression algorithm.</span></span> <span data-ttu-id="84413-128">Es gibt viele beliebte Tools, die Sie verwenden können, um <xref:System.IO.Compression.GZipStream>-Objekte zu dekomprimieren, die in eine *GZ*-Datei geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="84413-128">You can decompress <xref:System.IO.Compression.GZipStream> objects that are written to a *.gz* file by using many common tools.</span></span> <span data-ttu-id="84413-129">Das folgende Beispiel zeigt, wie Sie ein Dateiverzeichnis mithilfe der <xref:System.IO.Compression.GZipStream>-Klasse komprimieren und dekomprimieren:</span><span class="sxs-lookup"><span data-stu-id="84413-129">The following example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class:</span></span>

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a><span data-ttu-id="84413-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84413-130">See also</span></span>

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [<span data-ttu-id="84413-131">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="84413-131">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
