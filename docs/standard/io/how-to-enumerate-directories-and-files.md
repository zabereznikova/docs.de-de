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
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="da2e5-102">Gewusst wie: Auflisten von Verzeichnissen und Dateien</span><span class="sxs-lookup"><span data-stu-id="da2e5-102">How to: Enumerate Directories and Files</span></span>
<span data-ttu-id="da2e5-103">Auflisten von Verzeichnissen und Dateien mithilfe von Methoden, die eine aufzählbare Auflistung von Zeichenfolgen in ihren Namen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="da2e5-103">You can enumerate directories and files by using methods that return an enumerable collection of strings of their names.</span></span> <span data-ttu-id="da2e5-104">Sie können auch Methoden, mit denen eine aufzählbare Auflistung von <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, oder <xref:System.IO.FileSystemInfo> Objekte.</span><span class="sxs-lookup"><span data-stu-id="da2e5-104">You can also use methods that return an enumerable collection of <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span> <span data-ttu-id="da2e5-105">Aufzählbare Auflistungen ermöglichen eine bessere Leistung als Arrays, bei der Arbeit mit großen Auflistungen von Verzeichnissen und Dateien.</span><span class="sxs-lookup"><span data-stu-id="da2e5-105">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span>  
  
 <span data-ttu-id="da2e5-106">Sie können auch aufzählbare Auflistungen, die von diesen Methoden abgerufen, geben Sie die <xref:System.Collections.Generic.IEnumerable%601> -Parameter für Konstruktoren Auflistung Klassen wie der <xref:System.Collections.Generic.List%601> Klasse.</span><span class="sxs-lookup"><span data-stu-id="da2e5-106">You can also use enumerable collections obtained from these methods to supply the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes such as the <xref:System.Collections.Generic.List%601> class.</span></span>  
  
 <span data-ttu-id="da2e5-107">Wenn Sie nur die Namen von Verzeichnissen oder Dateien abrufen möchten, verwenden Sie die Enumerationsmethoden von der <xref:System.IO.Directory> Klasse.</span><span class="sxs-lookup"><span data-stu-id="da2e5-107">If you want to obtain only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="da2e5-108">Wenn Sie andere Eigenschaften von Verzeichnissen oder Dateien abrufen möchten, verwenden Sie die <xref:System.IO.DirectoryInfo> und <xref:System.IO.FileSystemInfo> Klassen.</span><span class="sxs-lookup"><span data-stu-id="da2e5-108">If you want to obtain other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
 <span data-ttu-id="da2e5-109">Die folgende Tabelle enthält eine Anleitung für die Methoden, die aufzählbare Auflistungen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="da2e5-109">The following table provides a guide to the methods that return enumerable collections.</span></span>  
  
|<span data-ttu-id="da2e5-110">Auflisten</span><span class="sxs-lookup"><span data-stu-id="da2e5-110">To enumerate</span></span>|<span data-ttu-id="da2e5-111">Aufzählbare Auflistung zurückzugebenden</span><span class="sxs-lookup"><span data-stu-id="da2e5-111">Enumerable collection to return</span></span>|<span data-ttu-id="da2e5-112">Zu verwendende Replikationsmethode</span><span class="sxs-lookup"><span data-stu-id="da2e5-112">Method to use</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="da2e5-113">Verzeichnisse</span><span class="sxs-lookup"><span data-stu-id="da2e5-113">Directories</span></span>|<span data-ttu-id="da2e5-114">Verzeichnisnamen</span><span class="sxs-lookup"><span data-stu-id="da2e5-114">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="da2e5-115">Verzeichnisinformationen (<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="da2e5-115">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="da2e5-116">Dateien</span><span class="sxs-lookup"><span data-stu-id="da2e5-116">Files</span></span>|<span data-ttu-id="da2e5-117">Dateinamen</span><span class="sxs-lookup"><span data-stu-id="da2e5-117">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="da2e5-118">Dateiinformationen (<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="da2e5-118">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="da2e5-119">Systeminformationen</span><span class="sxs-lookup"><span data-stu-id="da2e5-119">File system information</span></span>|<span data-ttu-id="da2e5-120">Dateisystemeinträgen</span><span class="sxs-lookup"><span data-stu-id="da2e5-120">File system entries</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="da2e5-121">Informationen zum Dateisystem (<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="da2e5-121">File system information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="da2e5-122">Obwohl Sie sofort alle Dateien in den Unterverzeichnissen des übergeordneten Verzeichnisses mit auflisten können die <xref:System.IO.SearchOption.AllDirectories> Option gebotenen Suchen der <xref:System.IO.SearchOption> -Enumeration, die vor nicht autorisiertem Zugriffsausnahmen (<xref:System.UnauthorizedAccessException>) kann dazu führen, dass die Enumeration unvollständig sein.</span><span class="sxs-lookup"><span data-stu-id="da2e5-122">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> search option provided by the <xref:System.IO.SearchOption> enumeration, unauthorized access exceptions (<xref:System.UnauthorizedAccessException>) may cause the enumeration to be incomplete.</span></span> <span data-ttu-id="da2e5-123">Wenn diese Ausnahmen möglich sind, können Sie sie abfangen und fortsetzen, indem zuerst Auflisten von Verzeichnissen und Dateien dann aufzählt.</span><span class="sxs-lookup"><span data-stu-id="da2e5-123">If these exceptions are possible, you can catch them and continue by first enumerating directories and then enumerating files.</span></span>  
  
### <a name="to-enumerate-directory-names"></a><span data-ttu-id="da2e5-124">Verzeichnisnamen auflisten</span><span class="sxs-lookup"><span data-stu-id="da2e5-124">To enumerate directory names</span></span>  
  
-   <span data-ttu-id="da2e5-125">Verwenden der <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> Methode, um eine Liste von Verzeichnisnamen in einem angegebenen Pfad der obersten Ebene abzurufen.</span><span class="sxs-lookup"><span data-stu-id="da2e5-125">Use the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to obtain a list of the top-level directory names in a specified path.</span></span>  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a><span data-ttu-id="da2e5-126">Dateinamen in einem Verzeichnis und die Unterverzeichnisse aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="da2e5-126">To enumerate file names in a directory and subdirectories</span></span>  
  
-   <span data-ttu-id="da2e5-127">Verwenden der <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> Methode, um ein Verzeichnis und (optional) der Unterverzeichnisse durchsucht, und um eine Liste von Dateinamen abzurufen, die einem angegebenen Suchmuster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="da2e5-127">Use the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to search a directory and (optionally) its subdirectories, and to obtain a list of file names that match a specified search pattern.</span></span>  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a><span data-ttu-id="da2e5-128">Zum Aufzählen einer Auflistung von DirectoryInfo-Objekte</span><span class="sxs-lookup"><span data-stu-id="da2e5-128">To enumerate a collection of DirectoryInfo objects</span></span>  
  
-   <span data-ttu-id="da2e5-129">Verwenden der <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> Methode, um eine Auflistung von Verzeichnissen der obersten Ebene abzurufen.</span><span class="sxs-lookup"><span data-stu-id="da2e5-129">Use the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to obtain a collection of top-level directories.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a><span data-ttu-id="da2e5-130">Zum Aufzählen einer Auflistung von FileInfo-Objekten in allen Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="da2e5-130">To enumerate a collection of FileInfo objects in all directories</span></span>  
  
-   <span data-ttu-id="da2e5-131">Verwenden der <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> Methode zum Abrufen einer Auflistung von Dateien, die in allen Verzeichnissen einem angegebenen Suchmuster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="da2e5-131">Use the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to obtain a collection of files that match a specified search pattern in all directories.</span></span> <span data-ttu-id="da2e5-132">In diesem Beispiel wird zuerst listet Verzeichnisse der obersten Ebene zum Abfangen von Ausnahmen nicht autorisierten Zugriff auf und zählt dann die Dateien.</span><span class="sxs-lookup"><span data-stu-id="da2e5-132">This example first enumerates the top-level directories to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="da2e5-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da2e5-133">See Also</span></span>  
 [<span data-ttu-id="da2e5-134">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="da2e5-134">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
