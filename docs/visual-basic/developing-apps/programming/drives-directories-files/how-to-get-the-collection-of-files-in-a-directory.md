---
title: "Gewusst wie: Abrufen einer Auflistung der Dateien in einem Verzeichnis in Visual Basic"
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
- folders, working with
- files, accessing
ms.assetid: 6c8ba7e8-dd37-4853-92bf-762b67c98160
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
ms.openlocfilehash: 023fb90622b45fe0067cd146f62bc3edb326b5ef
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-get-the-collection-of-files-in-a-directory-in-visual-basic"></a><span data-ttu-id="04588-102">Gewusst wie: Abrufen einer Auflistung der Dateien in einem Verzeichnis in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04588-102">How to: Get the Collection of Files in a Directory in Visual Basic</span></span>
<span data-ttu-id="04588-103">Die Überladungen der <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName>-Methode geben eine schreibgeschützte Sammlung an Zeichenfolgen zurück, die die Namen der Dateien innerhalb eines Verzeichnisses darstellen:</span><span class="sxs-lookup"><span data-stu-id="04588-103">The overloads of the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> method return a read-only collection of strings representing the names of the files within a directory:</span></span>  
  
-   <span data-ttu-id="04588-104">Verwenden Sie die <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29>-Überladung für eine einfache Dateisuche in einem angegebenen Verzeichnis, ohne Unterverzeichnisse zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="04588-104">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29> overload for a simple file search in a specified directory, without searching subdirectories.</span></span>  
  
-   <span data-ttu-id="04588-105">Verwenden Sie die <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])>-Überladung, um zusätzliche Optionen für Ihre Suche anzugeben.</span><span class="sxs-lookup"><span data-stu-id="04588-105">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])> overload to specify additional options for your search.</span></span> <span data-ttu-id="04588-106">Sie können die `wildCards`-Parameter verwenden, um ein Suchmuster anzugeben.</span><span class="sxs-lookup"><span data-stu-id="04588-106">You can use the `wildCards` parameter to specify a search pattern.</span></span> <span data-ttu-id="04588-107">Legen Sie zum Einschließen der Unterverzeichnisse in die Suche den Parameter `searchType` auf <xref:Microsoft.VisualBasic.FileIO.SearchOption.SearchAllSubDirectories?displayProperty=fullName> fest.</span><span class="sxs-lookup"><span data-stu-id="04588-107">To include subdirectories in the search, set the `searchType` parameter to <xref:Microsoft.VisualBasic.FileIO.SearchOption.SearchAllSubDirectories?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="04588-108">Es wird eine leere Sammlung zurückgegeben, wenn keine Dateien dem angegebenen Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="04588-108">An empty collection is returned if no files matching the specified pattern are found.</span></span>  
  
### <a name="to-list-files-in-a-directory"></a><span data-ttu-id="04588-109">So listen Sie Dateien in einem Verzeichnis auf</span><span class="sxs-lookup"><span data-stu-id="04588-109">To list files in a directory</span></span>  
  
-   <span data-ttu-id="04588-110">Verwenden Sie eine der <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName>-Methodenüberladungen, geben Sie den Namen und Pfad des zu durchsuchenden Verzeichnisses im Parameter `directory` an.</span><span class="sxs-lookup"><span data-stu-id="04588-110">Use one of the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> method overloads, supplying the name and path of the directory to search in the `directory` parameter.</span></span> <span data-ttu-id="04588-111">Im folgenden Beispiel werden alle Dateien im Verzeichnis zurückgegeben und `ListBox1` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="04588-111">The following example returns all files in the directory and adds them to `ListBox1`.</span></span>  
  
     <span data-ttu-id="04588-112">[!code-vb[VbVbcnMyFileSystem#32](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-get-the-collection-of-files-in-a-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="04588-112">[!code-vb[VbVbcnMyFileSystem#32](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-get-the-collection-of-files-in-a-directory_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="04588-113">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="04588-113">Robust Programming</span></span>  
 <span data-ttu-id="04588-114">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="04588-114">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="04588-115">Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="04588-115">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="04588-116">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="04588-116">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="04588-117">`directory` ist nicht vorhanden (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="04588-117">`directory` does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="04588-118">`directory` verweist auf eine vorhandene Datei (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="04588-118">`directory` points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="04588-119">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="04588-119">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="04588-120">Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="04588-120">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="04588-121">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="04588-121">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="04588-122">Der Benutzer verfügt nicht über die erforderlichen Berechtigungen (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="04588-122">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04588-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04588-123">See Also</span></span>  
 <span data-ttu-id="04588-124"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A></span><span class="sxs-lookup"><span data-stu-id="04588-124"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A></span></span>   
 <span data-ttu-id="04588-125">[Gewusst wie: Suchen nach Dateien mit einem bestimmten Muster](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md) </span><span class="sxs-lookup"><span data-stu-id="04588-125">[How to: Find Files with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md) </span></span>  
 [<span data-ttu-id="04588-126">Gewusst wie: Suchen nach Unterverzeichnissen mit einem bestimmten Muster</span><span class="sxs-lookup"><span data-stu-id="04588-126">How to: Find Subdirectories with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)

