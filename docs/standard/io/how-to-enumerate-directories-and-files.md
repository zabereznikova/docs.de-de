---
title: 'Vorgehensweise: Auflisten von Verzeichnissen und Dateien'
description: Erfahren Sie, wie Sie in .NET Verzeichnisse und Dateien mithilfe von aufzählbaren Sammlungen auflisten, die eine bessere Leistung als Arrays bieten können.
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
ms.openlocfilehash: 276668f4a3eee89610a81b1256820770d1f72dc3
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662575"
---
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="3c3bc-103">Vorgehensweise: Auflisten von Verzeichnissen und Dateien</span><span class="sxs-lookup"><span data-stu-id="3c3bc-103">How to: Enumerate directories and files</span></span>
<span data-ttu-id="3c3bc-104">Aufzählbare Sammlungen bieten bei der Arbeit mit großen Sammlungen von Verzeichnissen und Dateien eine bessere Leistung als Arrays.</span><span class="sxs-lookup"><span data-stu-id="3c3bc-104">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span> <span data-ttu-id="3c3bc-105">Verwenden Sie zum Auflisten von Verzeichnissen und Dateien Methoden, die eine aufzählbare Collection von Verzeichnis- oder Dateinamen zurückgeben, oder ihre <xref:System.IO.DirectoryInfo>-, <xref:System.IO.FileInfo>- oder <xref:System.IO.FileSystemInfo>-Objekte.</span><span class="sxs-lookup"><span data-stu-id="3c3bc-105">To enumerate directories and files, use methods that return an enumerable collection of directory or file names, or their <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span>  
  
<span data-ttu-id="3c3bc-106">Wenn Sie nur die Namen von Verzeichnissen oder Dateien suchen und zurückgegeben möchten, verwenden Sie die Enumerationsmethoden der <xref:System.IO.Directory>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="3c3bc-106">If you want to search and return only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="3c3bc-107">Wenn Sie andere Eigenschaften von Verzeichnissen oder Dateien abrufen möchten, verwenden Sie die <xref:System.IO.DirectoryInfo>- und <xref:System.IO.FileSystemInfo>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="3c3bc-107">If you want to search and return other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
<span data-ttu-id="3c3bc-108">Sie können die aufzählbaren Auflistungen dieser Methoden als <xref:System.Collections.Generic.IEnumerable%601>-Parameter für Konstruktoren von Auflistungsklassen wie <xref:System.Collections.Generic.List%601> verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c3bc-108">You can use enumerable collections from these methods as the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes like <xref:System.Collections.Generic.List%601>.</span></span>  
  
<span data-ttu-id="3c3bc-109">In der folgenden Tabelle werden die Methoden zusammengefasst, die aufzählbare Auflistungen von Dateien und Verzeichnissen zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="3c3bc-109">The following table summarizes the methods that return enumerable collections of files and directories:</span></span>  
  
|<span data-ttu-id="3c3bc-110">Zum Abrufen von</span><span class="sxs-lookup"><span data-stu-id="3c3bc-110">To search and return</span></span>|<span data-ttu-id="3c3bc-111">Zu verwendende Methode</span><span class="sxs-lookup"><span data-stu-id="3c3bc-111">Use method</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="3c3bc-112">Verzeichnisnamen</span><span class="sxs-lookup"><span data-stu-id="3c3bc-112">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3c3bc-113">Verzeichnisinformationen (<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="3c3bc-113">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3c3bc-114">Dateinamen</span><span class="sxs-lookup"><span data-stu-id="3c3bc-114">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3c3bc-115">Dateiinformationen (<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="3c3bc-115">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3c3bc-116">Namen von Dateisystemeinträgen</span><span class="sxs-lookup"><span data-stu-id="3c3bc-116">File system entry names</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3c3bc-117">Informationen zu Dateisystemeinträgen (<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="3c3bc-117">File system entry information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3c3bc-118">Verzeichnis- und Dateinamen</span><span class="sxs-lookup"><span data-stu-id="3c3bc-118">Directory and file names</span></span> |<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  

> [!NOTE]
> <span data-ttu-id="3c3bc-119">Obwohl Sie alle Dateien in den Unterverzeichnissen eines übergeordneten Verzeichnisses mithilfe der <xref:System.IO.SearchOption.AllDirectories>-Option der optionalen <xref:System.IO.SearchOption>-Enumeration sofort aufzählen können, können die Enumerationen aufgrund von <xref:System.UnauthorizedAccessException>-Fehlern unvollständig sein.</span><span class="sxs-lookup"><span data-stu-id="3c3bc-119">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> option of the optional <xref:System.IO.SearchOption> enumeration, <xref:System.UnauthorizedAccessException> errors may make the enumeration incomplete.</span></span> <span data-ttu-id="3c3bc-120">Sie können diese Ausnahmen erfassen, indem Sie zuerst die Verzeichnisse und dann die Dateien aufzählen.</span><span class="sxs-lookup"><span data-stu-id="3c3bc-120">You can catch these exceptions by first enumerating directories and then enumerating files.</span></span>  
  
## <a name="examples-use-the-directory-class"></a><span data-ttu-id="3c3bc-121">Beispiele: Verwenden der Directory-Klasse</span><span class="sxs-lookup"><span data-stu-id="3c3bc-121">Examples: Use the Directory class</span></span>  
  
<span data-ttu-id="3c3bc-122">Im folgenden Beispiel wird die <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType>-Methode verwendet, um eine Liste der Verzeichnisnamen im angegebenen Pfad abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3c3bc-122">The following example uses the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to get a list of the top-level directory names in a specified path.</span></span>  

[!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
[!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  

<span data-ttu-id="3c3bc-123">Im folgenden Beispiel wird die <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType>-Methode verwendet, um alle Dateinamen in einem Verzeichnis und den Unterverzeichnissen aufzuzählen, die einem bestimmten Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3c3bc-123">The following example uses the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to recursively enumerate all file names in a directory and subdirectories that match a certain pattern.</span></span> <span data-ttu-id="3c3bc-124">Anschließend wird jede Zeile jeder Datei gelesen, und die Zeilen, die die angegebene Zeichenfolge enthalten, werden samt Dateinamen und Pfaden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3c3bc-124">It then reads each line of each file and displays the lines that contain a specified string, with their filenames and paths.</span></span>

[!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
[!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
## <a name="examples-use-the-directoryinfo-class"></a><span data-ttu-id="3c3bc-125">Beispiele: Verwenden der DirectoryInfo-Klasse</span><span class="sxs-lookup"><span data-stu-id="3c3bc-125">Examples: Use the DirectoryInfo class</span></span>  
  
<span data-ttu-id="3c3bc-126">Im folgenden Beispiel wird die <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>-Methode zum Auflisten einer Collection von Verzeichnissen verwendet, deren <xref:System.IO.FileSystemInfo.CreationTimeUtc>-Eigenschaft einen Zeitwert vor dem Wert von <xref:System.DateTime> enthält.</span><span class="sxs-lookup"><span data-stu-id="3c3bc-126">The following example uses the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to list a collection of top-level directories whose <xref:System.IO.FileSystemInfo.CreationTimeUtc> is earlier than a certain <xref:System.DateTime> value.</span></span>  

[!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs)]
[!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb)]  
  
<span data-ttu-id="3c3bc-127">Im folgenden Beispiel wird die <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>-Methode zum Auflisten aller Dateien verwendet, deren <xref:System.IO.FileInfo.Length>-Wert über 10 MB liegt.</span><span class="sxs-lookup"><span data-stu-id="3c3bc-127">The following example uses the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to list all files whose <xref:System.IO.FileInfo.Length> exceeds 10MB.</span></span> <span data-ttu-id="3c3bc-128">In diesem Beispiel werden zunächst die obersten Verzeichnisse aufgezählt, um mögliche Ausnahmen in Form nicht autorisierten Zugriffs abzufangen, und dann die Dateien.</span><span class="sxs-lookup"><span data-stu-id="3c3bc-128">This example first enumerates the top-level directories, to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  

[!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
[!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3c3bc-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c3bc-129">See also</span></span>

- [<span data-ttu-id="3c3bc-130">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="3c3bc-130">File and stream I/O</span></span>](index.md)
