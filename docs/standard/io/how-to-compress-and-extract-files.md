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
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="9dfd6-102">Gewusst wie: Komprimieren und Extrahieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="9dfd6-102">How to: Compress and Extract Files</span></span>
<span data-ttu-id="9dfd6-103">Die <xref:System.IO.Compression> -Namespace enthält die folgenden Typen zum Komprimieren und Dekomprimieren von Dateien und Streams.</span><span class="sxs-lookup"><span data-stu-id="9dfd6-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="9dfd6-104">Sie können auch diese Typen verwenden, lesen und ändern Sie den Inhalt einer komprimierten Datei:</span><span class="sxs-lookup"><span data-stu-id="9dfd6-104">You can also use these types to read and modify the contents of a compressed file:</span></span>  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 <span data-ttu-id="9dfd6-105">Die folgenden Beispiele zeigen einige der Funktionen, die Sie ausführen können, bei der Arbeit mit komprimierten Dateien.</span><span class="sxs-lookup"><span data-stu-id="9dfd6-105">The following examples show some of the functions you can perform when working with compressed files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dfd6-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9dfd6-106">Example</span></span>  
 <span data-ttu-id="9dfd6-107">In diesem Beispiel wird gezeigt, wie zum Erstellen und extrahieren die komprimierte Datei mit der Erweiterung ZIP-Datei mithilfe der <xref:System.IO.Compression.ZipFile> Klasse.</span><span class="sxs-lookup"><span data-stu-id="9dfd6-107">This example shows how to create and extract a compressed file that has a .zip file name extension by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="9dfd6-108">Der Inhalt eines Ordners in eine neue ZIP-Datei komprimiert und extrahiert dann Inhalt an einen neuen Ordner.</span><span class="sxs-lookup"><span data-stu-id="9dfd6-108">It compresses the contents of a folder into a new .zip file and then extracts that content to a new folder.</span></span> <span data-ttu-id="9dfd6-109">Verwenden der <xref:System.IO.Compression.ZipFile> -Klasse, die Sie verweisen müssen die `System.IO.Compression.FileSystem` Assembly im Projekt.</span><span class="sxs-lookup"><span data-stu-id="9dfd6-109">To use the <xref:System.IO.Compression.ZipFile> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="9dfd6-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9dfd6-110">Example</span></span>  
 <span data-ttu-id="9dfd6-111">Im nächste Beispiel veranschaulicht die Iteration durch den Inhalt einer vorhandenen ZIP-Datei, und Extrahieren von Dateien mit der Erweiterung ".txt".</span><span class="sxs-lookup"><span data-stu-id="9dfd6-111">The next example shows how to iterate through the contents of an existing .zip file and extract files that have a .txt extension.</span></span> <span data-ttu-id="9dfd6-112">Er verwendet die <xref:System.IO.Compression.ZipArchive> Klasse, um eine vorhandene ZIP-Datei zugreifen und die <xref:System.IO.Compression.ZipArchiveEntry> Klasse, um die einzelnen Einträge in der komprimierten Datei zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9dfd6-112">It uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries in the compressed file.</span></span> <span data-ttu-id="9dfd6-113">Er verwendet eine Erweiterungsmethode (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) für die <xref:System.IO.Compression.ZipArchiveEntry> Objekt.</span><span class="sxs-lookup"><span data-stu-id="9dfd6-113">It uses an extension method (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) for the <xref:System.IO.Compression.ZipArchiveEntry> object.</span></span> <span data-ttu-id="9dfd6-114">Die Erweiterungsmethode steht in der <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="9dfd6-114">The extension method is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="9dfd6-115">Verwenden der <xref:System.IO.Compression.ZipFileExtensions> -Klasse, die Sie verweisen müssen die `System.IO.Compression.FileSystem` Assembly im Projekt.</span><span class="sxs-lookup"><span data-stu-id="9dfd6-115">To use the <xref:System.IO.Compression.ZipFileExtensions> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="9dfd6-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9dfd6-116">Example</span></span>  
 <span data-ttu-id="9dfd6-117">Im nächste Beispiel wird die <xref:System.IO.Compression.ZipArchive> -Klasse für den Zugriff auf eine vorhandene ZIP-Datei und fügt eine neue Datei zur komprimierten Datei.</span><span class="sxs-lookup"><span data-stu-id="9dfd6-117">The next example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and adds a new file to the compressed file.</span></span> <span data-ttu-id="9dfd6-118">Die neue Datei ruft komprimiert, wenn Sie ihn an die vorhandene ZIP-Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9dfd6-118">The new file gets compressed when you add it to the existing .zip file.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="9dfd6-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9dfd6-119">Example</span></span>  
 <span data-ttu-id="9dfd6-120">Sie können auch die <xref:System.IO.Compression.GZipStream> und <xref:System.IO.Compression.DeflateStream> Klassen zum Komprimieren und Dekomprimieren von Daten.</span><span class="sxs-lookup"><span data-stu-id="9dfd6-120">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="9dfd6-121">Sie verwenden denselben Komprimierungsalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="9dfd6-121">They use the same compression algorithm.</span></span> <span data-ttu-id="9dfd6-122">Komprimierte <xref:System.IO.Compression.GZipStream> Objekte, die in eine Datei geschrieben werden, mit der Erweiterung der .gz können viele häufig verwendete Tools neben den bereitgestellten Methoden mit dekomprimiert werden <xref:System.IO.Compression.GZipStream>.</span><span class="sxs-lookup"><span data-stu-id="9dfd6-122">Compressed <xref:System.IO.Compression.GZipStream> objects that are written to a file that has an extension of .gz can be decompressed by using many common tools in addition to the methods provided by <xref:System.IO.Compression.GZipStream>.</span></span> <span data-ttu-id="9dfd6-123">In diesem Beispiel wird gezeigt, wie zum Komprimieren und Dekomprimieren von Dateien in einem Verzeichnis mithilfe der <xref:System.IO.Compression.GZipStream> Klasse.</span><span class="sxs-lookup"><span data-stu-id="9dfd6-123">This example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class.</span></span>  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="9dfd6-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9dfd6-124">See Also</span></span>  
 <xref:System.IO.Compression.ZipArchive>  
 <xref:System.IO.Compression.ZipFile>  
 <xref:System.IO.Compression.ZipArchiveEntry>  
 <xref:System.IO.Compression.DeflateStream>  
 <xref:System.IO.Compression.GZipStream>  
 [<span data-ttu-id="9dfd6-125">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="9dfd6-125">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
