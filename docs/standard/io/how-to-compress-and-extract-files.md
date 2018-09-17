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
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="32acf-102">Gewusst wie: Komprimieren und Extrahieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="32acf-102">How to: Compress and extract files</span></span>

<span data-ttu-id="32acf-103">Der <xref:System.IO.Compression>-Namespace enthält die folgenden Typen zum Komprimieren und Dekomprimieren von Dateien und Streams.</span><span class="sxs-lookup"><span data-stu-id="32acf-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="32acf-104">Sie können diese Typen auch verwenden, um den Inhalt einer komprimierten Datei zu lesen und zu ändern:</span><span class="sxs-lookup"><span data-stu-id="32acf-104">You can also use these types to read and modify the contents of a compressed file:</span></span>

- <xref:System.IO.Compression.ZipFile>

- <xref:System.IO.Compression.ZipArchive>

- <xref:System.IO.Compression.ZipArchiveEntry>

- <xref:System.IO.Compression.DeflateStream>

- <xref:System.IO.Compression.GZipStream>

<span data-ttu-id="32acf-105">Die folgenden Beispiele zeigen einige der Funktionen, die Sie beim Arbeiten mit komprimierten Dateien ausführen können.</span><span class="sxs-lookup"><span data-stu-id="32acf-105">The following examples show some of the functions you can perform when working with compressed files.</span></span>

## <a name="example-1---create-and-extract-a-zip-file"></a><span data-ttu-id="32acf-106">Beispiel 1: Erstellen und Extrahieren einer ZIP-Datei</span><span class="sxs-lookup"><span data-stu-id="32acf-106">Example 1 - Create and extract a .zip file</span></span>

<span data-ttu-id="32acf-107">Das folgende Beispiel zeigt, wie Sie mithilfe der <xref:System.IO.Compression.ZipFile>-Klasse eine komprimierte Datei mit der Erweiterung „ZIP“ erstellen und extrahieren.</span><span class="sxs-lookup"><span data-stu-id="32acf-107">The following example shows how to create and extract a compressed file that has a .zip file name extension by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="32acf-108">Das Beispiel komprimiert den Inhalt eines Ordners in eine neue ZIP-Datei und extrahiert diese dann in einen neuen Ordner.</span><span class="sxs-lookup"><span data-stu-id="32acf-108">It compresses the contents of a folder into a new .zip file and then extracts that content to a new folder.</span></span> <span data-ttu-id="32acf-109">Um die <xref:System.IO.Compression.ZipFile>-Klasse zu verwenden, müssen Sie auf die `System.IO.Compression.FileSystem`-Assembly in Ihrem Projekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="32acf-109">To use the <xref:System.IO.Compression.ZipFile> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2---extract-specific-file-extensions"></a><span data-ttu-id="32acf-110">Beispiel 2: Extrahieren bestimmter Dateierweiterungen</span><span class="sxs-lookup"><span data-stu-id="32acf-110">Example 2 - Extract specific file extensions</span></span>

<span data-ttu-id="32acf-111">Das nächste Beispiel zeigt, wie Sie den Inhalt einer vorhandenen ZIP-Datei durchlaufen und Dateien mit der Erweiterung „TXT“ extrahieren.</span><span class="sxs-lookup"><span data-stu-id="32acf-111">The next example shows how to iterate through the contents of an existing .zip file and extract files that have a .txt extension.</span></span> <span data-ttu-id="32acf-112">Es verwendet die <xref:System.IO.Compression.ZipArchive>-Klasse, um auf eine vorhandene ZIP-Datei zuzugreifen, und die <xref:System.IO.Compression.ZipArchiveEntry>-Klasse, um die einzelnen Einträge in der komprimierten Datei zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="32acf-112">It uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries in the compressed file.</span></span> <span data-ttu-id="32acf-113">Es verwendet eine Erweiterungsmethode (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) für das <xref:System.IO.Compression.ZipArchiveEntry>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="32acf-113">It uses an extension method (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) for the <xref:System.IO.Compression.ZipArchiveEntry> object.</span></span> <span data-ttu-id="32acf-114">Die Erweiterungsmethode ist in der <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>-Klasse verfügbar.</span><span class="sxs-lookup"><span data-stu-id="32acf-114">The extension method is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="32acf-115">Um die <xref:System.IO.Compression.ZipFileExtensions>-Klasse zu verwenden, müssen Sie auf die `System.IO.Compression.FileSystem`-Assembly in Ihrem Projekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="32acf-115">To use the <xref:System.IO.Compression.ZipFileExtensions> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32acf-116">Beim Extrahieren von Dateien müssen Sie auf schädliche Dateipfade achten, die aus dem Verzeichnis weisen können, in das Sie extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="32acf-116">When unzipping files, you must look for malicious file paths which can escape out of the directory where you want to unzip into.</span></span> <span data-ttu-id="32acf-117">Dies wird als Path Traversal-Angriff bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="32acf-117">This is known as a path traversal attack.</span></span>

<span data-ttu-id="32acf-118">Das folgende Beispiel zeigt die Überprüfung auf schädliche Dateipfade und bietet eine sichere Möglichkeit zum Extrahieren:</span><span class="sxs-lookup"><span data-stu-id="32acf-118">The following example demonstrates how to check for malicious file paths and provides a safe way to unzip:</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3---add-a-new-file-to-an-existing-zip-file"></a><span data-ttu-id="32acf-119">Beispiel 3: Hinzufügen einer neuen Datei zu einer vorhandenen ZIP-Datei</span><span class="sxs-lookup"><span data-stu-id="32acf-119">Example 3 - Add a new file to an existing .zip file</span></span>

<span data-ttu-id="32acf-120">Im folgenden Beispiel wird die <xref:System.IO.Compression.ZipArchive>-Klasse verwendet, um auf eine vorhandene ZIP-Datei zuzugreifen, und der komprimierten Datei eine neue Datei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="32acf-120">The following example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and adds a new file to the compressed file.</span></span> <span data-ttu-id="32acf-121">Die neue Datei wird komprimiert, wenn Sie sie zur vorhandenen ZIP-Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="32acf-121">The new file gets compressed when you add it to the existing .zip file.</span></span>

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4---compress-and-decompress-a-directory-of-gz-files"></a><span data-ttu-id="32acf-122">Beispiel 4: Komprimieren und Dekomprimieren eines Verzeichnisses von GZ-Dateien</span><span class="sxs-lookup"><span data-stu-id="32acf-122">Example 4 - Compress and decompress a directory of .gz files</span></span>

<span data-ttu-id="32acf-123">Sie können auch die Klassen <xref:System.IO.Compression.GZipStream> und <xref:System.IO.Compression.DeflateStream> verwenden, um Daten zu komprimieren und zu dekomprimieren.</span><span class="sxs-lookup"><span data-stu-id="32acf-123">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="32acf-124">Der Komprimierungsalgorithmus ist der gleiche.</span><span class="sxs-lookup"><span data-stu-id="32acf-124">They use the same compression algorithm.</span></span> <span data-ttu-id="32acf-125">Komprimierte <xref:System.IO.Compression.GZipStream>-Objekte, die in eine Datei mit der Erweiterung „GZ“ geschrieben werden, können mit den von <xref:System.IO.Compression.GZipStream> bereitgestellten Methoden sowie mit vielen häufig verwendeten Tools dekomprimiert werden.</span><span class="sxs-lookup"><span data-stu-id="32acf-125">Compressed <xref:System.IO.Compression.GZipStream> objects that are written to a file that has an extension of .gz can be decompressed by using many common tools in addition to the methods provided by <xref:System.IO.Compression.GZipStream>.</span></span> <span data-ttu-id="32acf-126">Das folgende Beispiel zeigt, wie Sie ein Dateiverzeichnis mithilfe der <xref:System.IO.Compression.GZipStream>-Klasse komprimieren und dekomprimieren:</span><span class="sxs-lookup"><span data-stu-id="32acf-126">The following example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class:</span></span>

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a><span data-ttu-id="32acf-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32acf-127">See also</span></span>

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [<span data-ttu-id="32acf-128">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="32acf-128">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
