---
title: 'Vorgehensweise: Auflisten von Verzeichnissen und Dateien'
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
ms.openlocfilehash: bcb10426175c1f2cabeec6d8d4f8d2ed74e5e3b4
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291876"
---
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="ff093-102">Vorgehensweise: Auflisten von Verzeichnissen und Dateien</span><span class="sxs-lookup"><span data-stu-id="ff093-102">How to: Enumerate directories and files</span></span>
<span data-ttu-id="ff093-103">Aufzählbare Sammlungen bieten bei der Arbeit mit großen Sammlungen von Verzeichnissen und Dateien eine bessere Leistung als Arrays.</span><span class="sxs-lookup"><span data-stu-id="ff093-103">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span> <span data-ttu-id="ff093-104">Verwenden Sie zum Auflisten von Verzeichnissen und Dateien Methoden, die eine aufzählbare Collection von Verzeichnis- oder Dateinamen zurückgeben, oder ihre <xref:System.IO.DirectoryInfo>-, <xref:System.IO.FileInfo>- oder <xref:System.IO.FileSystemInfo>-Objekte.</span><span class="sxs-lookup"><span data-stu-id="ff093-104">To enumerate directories and files, use methods that return an enumerable collection of directory or file names, or their <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span>  
  
<span data-ttu-id="ff093-105">Wenn Sie nur die Namen von Verzeichnissen oder Dateien suchen und zurückgegeben möchten, verwenden Sie die Enumerationsmethoden der <xref:System.IO.Directory>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="ff093-105">If you want to search and return only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="ff093-106">Wenn Sie andere Eigenschaften von Verzeichnissen oder Dateien abrufen möchten, verwenden Sie die <xref:System.IO.DirectoryInfo>- und <xref:System.IO.FileSystemInfo>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="ff093-106">If you want to search and return other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
<span data-ttu-id="ff093-107">Sie können die aufzählbaren Auflistungen dieser Methoden als <xref:System.Collections.Generic.IEnumerable%601>-Parameter für Konstruktoren von Auflistungsklassen wie <xref:System.Collections.Generic.List%601> verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff093-107">You can use enumerable collections from these methods as the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes like <xref:System.Collections.Generic.List%601>.</span></span>  
  
<span data-ttu-id="ff093-108">In der folgenden Tabelle werden die Methoden zusammengefasst, die aufzählbare Auflistungen von Dateien und Verzeichnissen zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="ff093-108">The following table summarizes the methods that return enumerable collections of files and directories:</span></span>  
  
|<span data-ttu-id="ff093-109">Zum Abrufen von</span><span class="sxs-lookup"><span data-stu-id="ff093-109">To search and return</span></span>|<span data-ttu-id="ff093-110">Zu verwendende Methode</span><span class="sxs-lookup"><span data-stu-id="ff093-110">Use method</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="ff093-111">Verzeichnisnamen</span><span class="sxs-lookup"><span data-stu-id="ff093-111">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ff093-112">Verzeichnisinformationen (<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="ff093-112">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ff093-113">Dateinamen</span><span class="sxs-lookup"><span data-stu-id="ff093-113">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ff093-114">Dateiinformationen (<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="ff093-114">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ff093-115">Namen von Dateisystemeinträgen</span><span class="sxs-lookup"><span data-stu-id="ff093-115">File system entry names</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ff093-116">Informationen zu Dateisystemeinträgen (<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="ff093-116">File system entry information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ff093-117">Verzeichnis- und Dateinamen</span><span class="sxs-lookup"><span data-stu-id="ff093-117">Directory and file names</span></span> |<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  

> [!NOTE]
> <span data-ttu-id="ff093-118">Obwohl Sie alle Dateien in den Unterverzeichnissen eines übergeordneten Verzeichnisses mithilfe der <xref:System.IO.SearchOption.AllDirectories>-Option der optionalen <xref:System.IO.SearchOption>-Enumeration sofort aufzählen können, können die Enumerationen aufgrund von <xref:System.UnauthorizedAccessException>-Fehlern unvollständig sein.</span><span class="sxs-lookup"><span data-stu-id="ff093-118">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> option of the optional <xref:System.IO.SearchOption> enumeration, <xref:System.UnauthorizedAccessException> errors may make the enumeration incomplete.</span></span> <span data-ttu-id="ff093-119">Sie können diese Ausnahmen erfassen, indem Sie zuerst die Verzeichnisse und dann die Dateien aufzählen.</span><span class="sxs-lookup"><span data-stu-id="ff093-119">You can catch these exceptions by first enumerating directories and then enumerating files.</span></span>  
  
## <a name="examples-use-the-directory-class"></a><span data-ttu-id="ff093-120">Beispiele: Verwenden der Directory-Klasse</span><span class="sxs-lookup"><span data-stu-id="ff093-120">Examples: Use the Directory class</span></span>  
  
<span data-ttu-id="ff093-121">Im folgenden Beispiel wird die <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType>-Methode verwendet, um eine Liste der Verzeichnisnamen im angegebenen Pfad abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ff093-121">The following example uses the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to get a list of the top-level directory names in a specified path.</span></span>  

[!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
[!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  

<span data-ttu-id="ff093-122">Im folgenden Beispiel wird die <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType>-Methode verwendet, um alle Dateinamen in einem Verzeichnis und den Unterverzeichnissen aufzuzählen, die einem bestimmten Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ff093-122">The following example uses the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to recursively enumerate all file names in a directory and subdirectories that match a certain pattern.</span></span> <span data-ttu-id="ff093-123">Anschließend wird jede Zeile jeder Datei gelesen, und die Zeilen, die die angegebene Zeichenfolge enthalten, werden samt Dateinamen und Pfaden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff093-123">It then reads each line of each file and displays the lines that contain a specified string, with their filenames and paths.</span></span>

[!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
[!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
## <a name="examples-use-the-directoryinfo-class"></a><span data-ttu-id="ff093-124">Beispiele: Verwenden der DirectoryInfo-Klasse</span><span class="sxs-lookup"><span data-stu-id="ff093-124">Examples: Use the DirectoryInfo class</span></span>  
  
<span data-ttu-id="ff093-125">Im folgenden Beispiel wird die <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>-Methode zum Auflisten einer Collection von Verzeichnissen verwendet, deren <xref:System.IO.FileSystemInfo.CreationTimeUtc>-Eigenschaft einen Zeitwert vor dem Wert von <xref:System.DateTime> enthält.</span><span class="sxs-lookup"><span data-stu-id="ff093-125">The following example uses the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to list a collection of top-level directories whose <xref:System.IO.FileSystemInfo.CreationTimeUtc> is earlier than a certain <xref:System.DateTime> value.</span></span>  

[!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs)]
[!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb)]  
  
<span data-ttu-id="ff093-126">Im folgenden Beispiel wird die <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>-Methode zum Auflisten aller Dateien verwendet, deren <xref:System.IO.FileInfo.Length>-Wert über 10 MB liegt.</span><span class="sxs-lookup"><span data-stu-id="ff093-126">The following example uses the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to list all files whose <xref:System.IO.FileInfo.Length> exceeds 10MB.</span></span> <span data-ttu-id="ff093-127">In diesem Beispiel werden zunächst die obersten Verzeichnisse aufgezählt, um mögliche Ausnahmen in Form nicht autorisierten Zugriffs abzufangen, und dann die Dateien.</span><span class="sxs-lookup"><span data-stu-id="ff093-127">This example first enumerates the top-level directories, to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  

[!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
[!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ff093-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff093-128">See also</span></span>

- [<span data-ttu-id="ff093-129">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="ff093-129">File and stream I/O</span></span>](index.md)
