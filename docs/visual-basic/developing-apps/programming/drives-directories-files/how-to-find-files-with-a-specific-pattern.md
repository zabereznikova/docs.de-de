---
title: 'Gewusst wie: Suchen nach Dateien mit einem bestimmten Muster in Visual Basic'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- files, finding
- pattern matching
- patterns, matching
ms.assetid: 25e3b71d-b844-4293-9e4e-f06c5836b5cc
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5e5d7dc692bf68ebccc459e9cf3f92c3683b8145
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-files-with-a-specific-pattern-in-visual-basic"></a><span data-ttu-id="96a65-102">Gewusst wie: Suchen nach Dateien mit einem bestimmten Muster in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96a65-102">How to: Find Files with a Specific Pattern in Visual Basic</span></span>
<span data-ttu-id="96a65-103">Die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>-Methode gibt eine schreibgeschützte Auflistung von Zeichenfolgen zurück, die die Pfadnamen für die Dateien darstellen.</span><span class="sxs-lookup"><span data-stu-id="96a65-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> method returns a read-only collection of strings representing the path names for the files.</span></span> <span data-ttu-id="96a65-104">Sie können den `wildCards` -Parameter verwenden, um ein bestimmtes Muster anzugeben.</span><span class="sxs-lookup"><span data-stu-id="96a65-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span> <span data-ttu-id="96a65-105">Legen Sie zum Einschließen der Unterverzeichnisse in die Suche den Parameter `searchType` auf `SearchOption.SearchAllSubDirectories` fest.</span><span class="sxs-lookup"><span data-stu-id="96a65-105">If you would like to include subdirectories in the search, set the `searchType` parameter to `SearchOption.SearchAllSubDirectories`.</span></span>  
  
 <span data-ttu-id="96a65-106">Es wird eine leere Sammlung zurückgegeben, wenn keine Dateien dem angegebenen Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="96a65-106">An empty collection is returned if no files matching the specified pattern are found.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96a65-107">Informationen zur Rückgabe einer Dateiliste mit der `DirectoryInfo`-Klasse des `System.IO`-Namespace finden Sie unter <xref:System.IO.DirectoryInfo.GetFiles%2A>.</span><span class="sxs-lookup"><span data-stu-id="96a65-107">For information about returning a file list by using the `DirectoryInfo` class of the `System.IO` namespace, see <xref:System.IO.DirectoryInfo.GetFiles%2A>.</span></span>  
  
### <a name="to-find-files-with-a-specified-pattern"></a><span data-ttu-id="96a65-108">Suchen nach Dateien mit einem bestimmten Muster</span><span class="sxs-lookup"><span data-stu-id="96a65-108">To find files with a specified pattern</span></span>  
  
-   <span data-ttu-id="96a65-109">Verwenden Sie die `GetFiles`-Methode, die den Namen und Pfad des zu durchsuchenden Verzeichnisses bereitstellt, und die das Muster angibt.</span><span class="sxs-lookup"><span data-stu-id="96a65-109">Use the `GetFiles` method, supplying the name and path of the directory you want to search and specifying the pattern.</span></span> <span data-ttu-id="96a65-110">Im folgenden Beispiel werden alle Dateien mit der Erweiterung `.dll` im Verzeichnis zurückgegeben und `ListBox1` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="96a65-110">The following example returns all files with the extension `.dll` in the directory and adds them to `ListBox1`.</span></span>  
  
     <span data-ttu-id="96a65-111">[!code-vb[VbFileIOMisc#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-files-with-a-specific-pattern_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="96a65-111">[!code-vb[VbFileIOMisc#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-files-with-a-specific-pattern_1.vb)]</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="96a65-112">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="96a65-112">.NET Framework Security</span></span>  
 <span data-ttu-id="96a65-113">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="96a65-113">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="96a65-114">Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="96a65-114">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="96a65-115">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="96a65-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="96a65-116">`directory` ist nicht vorhanden (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="96a65-116">`directory` does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="96a65-117">`directory` verweist auf eine vorhandene Datei (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="96a65-117">`directory` points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="96a65-118">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="96a65-118">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="96a65-119">Der Pfad eines Datei- oder Ordnernamens enthält einen Doppelpunkt (:) oder weist ein ungültiges Format auf (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="96a65-119">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="96a65-120">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="96a65-120">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="96a65-121">Der Benutzer verfügt nicht über die erforderlichen Berechtigungen (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="96a65-121">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96a65-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96a65-122">See Also</span></span>  
 <span data-ttu-id="96a65-123"><xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A></span><span class="sxs-lookup"><span data-stu-id="96a65-123"><xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A></span></span>   
 <span data-ttu-id="96a65-124">[Gewusst wie: Suchen nach Unterverzeichnissen mit einem bestimmten Muster](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md) </span><span class="sxs-lookup"><span data-stu-id="96a65-124">[How to: Find Subdirectories with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md) </span></span>  
 <span data-ttu-id="96a65-125">[Problembehandlung: Lesen aus und Schreiben in Textdateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="96a65-125">[Troubleshooting: Reading from and Writing to Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md) </span></span>  
 [<span data-ttu-id="96a65-126">Gewusst wie: Abrufen einer Sammlung von Dateien in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="96a65-126">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)

