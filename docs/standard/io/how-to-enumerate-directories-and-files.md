---
title: 'Gewusst wie: Auflisten von Verzeichnissen und Dateien'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3de83395df9e8c89a92e85b96ddd15e9f0be6ad5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44207693"
---
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="0956d-102">Gewusst wie: Auflisten von Verzeichnissen und Dateien</span><span class="sxs-lookup"><span data-stu-id="0956d-102">How to: Enumerate Directories and Files</span></span>
<span data-ttu-id="0956d-103">Sie können Verzeichnisse und Dateien mithilfe von Methoden aufzählen, die eine aufzählbare Sammlung von Zeichenfolgen ihrer Namen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0956d-103">You can enumerate directories and files by using methods that return an enumerable collection of strings of their names.</span></span> <span data-ttu-id="0956d-104">Sie können auch Methoden verwenden, die eine aufzählbare Sammlung von <xref:System.IO.DirectoryInfo>-, <xref:System.IO.FileInfo>- oder <xref:System.IO.FileSystemInfo>-Objekten zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0956d-104">You can also use methods that return an enumerable collection of <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span> <span data-ttu-id="0956d-105">Aufzählbare Sammlungen bieten bei der Arbeit mit großen Sammlungen von Verzeichnissen und Dateien eine bessere Leistung als Arrays.</span><span class="sxs-lookup"><span data-stu-id="0956d-105">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span>  
  
 <span data-ttu-id="0956d-106">Sie können mit von diesen Methoden abgerufenen aufzählbaren Sammlungen auch den <xref:System.Collections.Generic.IEnumerable%601>-Parameter für Konstruktoren von Sammlungsklassen wie der <xref:System.Collections.Generic.List%601>-Klasse angeben.</span><span class="sxs-lookup"><span data-stu-id="0956d-106">You can also use enumerable collections obtained from these methods to supply the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes such as the <xref:System.Collections.Generic.List%601> class.</span></span>  
  
 <span data-ttu-id="0956d-107">Wenn Sie nur die Namen von Verzeichnissen oder Dateien abrufen möchten, verwenden Sie die Enumerationsmethoden der <xref:System.IO.Directory>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="0956d-107">If you want to obtain only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="0956d-108">Wenn Sie andere Eigenschaften von Verzeichnissen oder Dateien abrufen möchten, verwenden Sie die <xref:System.IO.DirectoryInfo>- und <xref:System.IO.FileSystemInfo>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="0956d-108">If you want to obtain other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
 <span data-ttu-id="0956d-109">Die folgende Tabelle enthält eine Anleitung für die Methoden, die aufzählbare Sammlungen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0956d-109">The following table provides a guide to the methods that return enumerable collections.</span></span>  
  
|<span data-ttu-id="0956d-110">Aufzuzählendes</span><span class="sxs-lookup"><span data-stu-id="0956d-110">To enumerate</span></span>|<span data-ttu-id="0956d-111">Zurückzugebende aufzählbare Sammlung</span><span class="sxs-lookup"><span data-stu-id="0956d-111">Enumerable collection to return</span></span>|<span data-ttu-id="0956d-112">Zu verwendende Methode</span><span class="sxs-lookup"><span data-stu-id="0956d-112">Method to use</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="0956d-113">Verzeichnisse</span><span class="sxs-lookup"><span data-stu-id="0956d-113">Directories</span></span>|<span data-ttu-id="0956d-114">Verzeichnisnamen</span><span class="sxs-lookup"><span data-stu-id="0956d-114">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="0956d-115">Verzeichnisinformationen (<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="0956d-115">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0956d-116">Dateien</span><span class="sxs-lookup"><span data-stu-id="0956d-116">Files</span></span>|<span data-ttu-id="0956d-117">Dateinamen</span><span class="sxs-lookup"><span data-stu-id="0956d-117">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="0956d-118">Dateiinformationen (<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="0956d-118">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0956d-119">Dateisysteminformationen</span><span class="sxs-lookup"><span data-stu-id="0956d-119">File system information</span></span>|<span data-ttu-id="0956d-120">Dateisystemeinträge</span><span class="sxs-lookup"><span data-stu-id="0956d-120">File system entries</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="0956d-121">Dateisysteminformationen (<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="0956d-121">File system information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="0956d-122">Sie können zwar mithilfe der <xref:System.IO.SearchOption.AllDirectories>-Suchoption der <xref:System.IO.SearchOption>-Enumeration sofort alle Dateien in den Unterverzeichnissen eines übergeordneten Verzeichnisses aufzählen, doch Ausnahmen in Form nicht autorisierten Zugriffs (<xref:System.UnauthorizedAccessException>) können dazu führen, dass die Enumeration unvollständig ist.</span><span class="sxs-lookup"><span data-stu-id="0956d-122">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> search option provided by the <xref:System.IO.SearchOption> enumeration, unauthorized access exceptions (<xref:System.UnauthorizedAccessException>) may cause the enumeration to be incomplete.</span></span> <span data-ttu-id="0956d-123">Wenn diese Ausnahmen möglich sind, können Sie sie abfangen und fortfahren, indem Sie zuerst Verzeichnisse und dann Dateien aufzählen.</span><span class="sxs-lookup"><span data-stu-id="0956d-123">If these exceptions are possible, you can catch them and continue by first enumerating directories and then enumerating files.</span></span>  
  
### <a name="to-enumerate-directory-names"></a><span data-ttu-id="0956d-124">So zählen Sie Verzeichnisnamen auf</span><span class="sxs-lookup"><span data-stu-id="0956d-124">To enumerate directory names</span></span>  
  
-   <span data-ttu-id="0956d-125">Rufen Sie mit der <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType>-Methode eine Liste von Verzeichnisnamen der obersten Ebene in einem angegebenen Pfad ab.</span><span class="sxs-lookup"><span data-stu-id="0956d-125">Use the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to obtain a list of the top-level directory names in a specified path.</span></span>  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a><span data-ttu-id="0956d-126">So zählen Sie Dateinamen in einem Verzeichnis und Unterverzeichnissen auf</span><span class="sxs-lookup"><span data-stu-id="0956d-126">To enumerate file names in a directory and subdirectories</span></span>  
  
-   <span data-ttu-id="0956d-127">Verwenden Sie die <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType>-Methode, um ein Verzeichnis und (optional) seine Unterverzeichnisse zu durchsuchen, und um eine Liste von Dateinamen abzurufen, die einem angegebenen Suchmuster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0956d-127">Use the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to search a directory and (optionally) its subdirectories, and to obtain a list of file names that match a specified search pattern.</span></span>  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a><span data-ttu-id="0956d-128">So zählen Sie eine Sammlung von DirectoryInfo-Objekten auf</span><span class="sxs-lookup"><span data-stu-id="0956d-128">To enumerate a collection of DirectoryInfo objects</span></span>  
  
-   <span data-ttu-id="0956d-129">Rufen Sie mit der <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>-Methode eine Sammlung von Verzeichnissen der obersten Ebene ab.</span><span class="sxs-lookup"><span data-stu-id="0956d-129">Use the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to obtain a collection of top-level directories.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a><span data-ttu-id="0956d-130">So zählen Sie eine Sammlung von FileInfo-Objekten in allen Verzeichnissen auf</span><span class="sxs-lookup"><span data-stu-id="0956d-130">To enumerate a collection of FileInfo objects in all directories</span></span>  
  
-   <span data-ttu-id="0956d-131">Rufen Sie mit der <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>-Methode in allen Verzeichnissen eine Sammlung von Dateien ab, die einem angegebenen Suchmuster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0956d-131">Use the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to obtain a collection of files that match a specified search pattern in all directories.</span></span> <span data-ttu-id="0956d-132">In diesem Beispiel werden zuerst die Verzeichnisse der obersten Ebene aufgezählt, um mögliche Ausnahmen in Form nicht autorisierten Zugriffs abzufangen, und dann die Dateien.</span><span class="sxs-lookup"><span data-stu-id="0956d-132">This example first enumerates the top-level directories to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0956d-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0956d-133">See also</span></span>

- [<span data-ttu-id="0956d-134">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="0956d-134">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
