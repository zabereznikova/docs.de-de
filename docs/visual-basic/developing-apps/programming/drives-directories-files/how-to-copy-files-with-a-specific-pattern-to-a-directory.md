---
title: 'Gewusst wie: Kopieren von Dateien mit einem bestimmten Muster in ein Verzeichnis in Visual Basic'
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
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files, copying
- CopyFile method, copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: f205d2ad-bbe5-4d55-8a40-acda21aa82dd
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 812fd59769da386f8d0b81eb80a4cd93c9764534
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-copy-files-with-a-specific-pattern-to-a-directory-in-visual-basic"></a><span data-ttu-id="8b220-102">Gewusst wie: Kopieren von Dateien mit einem bestimmten Muster in ein Verzeichnis in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8b220-102">How to: Copy Files with a Specific Pattern to a Directory in Visual Basic</span></span>
<span data-ttu-id="8b220-103">Die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> -Methode gibt eine schreibgeschützte Auflistung von Zeichenfolgen zurück, die die Pfadnamen für die Dateien darstellen.</span><span class="sxs-lookup"><span data-stu-id="8b220-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> method returns a read-only collection of strings representing the path names for the files.</span></span> <span data-ttu-id="8b220-104">Sie können den `wildCards` -Parameter verwenden, um ein bestimmtes Muster anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8b220-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span>  
  
 <span data-ttu-id="8b220-105">Wenn keine übereinstimmenden Dateien gefunden werden, wird eine leere Auflistung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8b220-105">An empty collection is returned if no matching files are found.</span></span>  
  
 <span data-ttu-id="8b220-106">Mit der <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> -Methode können Sie die Dateien in ein Verzeichnis kopieren.</span><span class="sxs-lookup"><span data-stu-id="8b220-106">You can use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> method to copy the files to a directory.</span></span>  
  
### <a name="to-copy-files-with-a-specific-pattern-to-a-directory"></a><span data-ttu-id="8b220-107">So kopieren Sie Dateien mit einem bestimmten Muster in ein Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="8b220-107">To copy files with a specific pattern to a directory</span></span>  
  
1.  <span data-ttu-id="8b220-108">Verwenden Sie die `GetFiles` -Methode, um die Liste der Dateien zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="8b220-108">Use the `GetFiles` method to return the list of files.</span></span> <span data-ttu-id="8b220-109">In diesem Beispiel werden alle RTF-Dateien im angegebenen Verzeichnis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8b220-109">This example returns all .rtf files in the specified directory.</span></span>  
  
     <span data-ttu-id="8b220-110">[!code-vb[VbFileIOMisc#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b220-110">[!code-vb[VbFileIOMisc#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_1.vb)]</span></span>  
  
2.  <span data-ttu-id="8b220-111">Verwenden Sie die `CopyFile` -Methode, um die Dateien zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="8b220-111">Use the `CopyFile` method to copy the files.</span></span> <span data-ttu-id="8b220-112">In diesem Beispiel werden die Dateien in das Verzeichnis `testdirectory`kopiert.</span><span class="sxs-lookup"><span data-stu-id="8b220-112">This example copies the files to the directory named `testdirectory`.</span></span>  
  
     <span data-ttu-id="8b220-113">[!code-vb[VbVbcnMyFileSystem#88](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b220-113">[!code-vb[VbVbcnMyFileSystem#88](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_2.vb)]</span></span>  
  
3.  <span data-ttu-id="8b220-114">Schließen Sie die `For` -Anweisung mit einer `Next` -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8b220-114">Close the `For` statement with a `Next` statement.</span></span>  
  
     <span data-ttu-id="8b220-115">[!code-vb[VbVbcnMyFileSystem#89](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b220-115">[!code-vb[VbVbcnMyFileSystem#89](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b220-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b220-116">Example</span></span>  
 <span data-ttu-id="8b220-117">Im folgenden Beispiel, das der vollständigen Fassung der oben aufgeführten Codeausschnitte entspricht, werden alle RTF-Dateien im angegebenen Verzeichnis in das Verzeichnis `testdirectory`kopiert.</span><span class="sxs-lookup"><span data-stu-id="8b220-117">The following example, which presents the above snippets in complete form, copies all .rtf files in the specified directory to the directory named `testdirectory`.</span></span>  
  
 <span data-ttu-id="8b220-118">[!code-vb[VbFileIOMisc#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b220-118">[!code-vb[VbFileIOMisc#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_4.vb)]</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8b220-119">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8b220-119">.NET Framework Security</span></span>  
 <span data-ttu-id="8b220-120">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="8b220-120">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="8b220-121">Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="8b220-121">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="8b220-122">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="8b220-122">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="8b220-123">Das Verzeichnis ist nicht vorhanden (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="8b220-123">The directory does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="8b220-124">Das Verzeichnis verweist auf eine vorhandene Datei (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="8b220-124">The directory points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="8b220-125">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="8b220-125">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="8b220-126">Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="8b220-126">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="8b220-127">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="8b220-127">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span> <span data-ttu-id="8b220-128">Der Benutzer verfügt nicht über die erforderlichen Berechtigungen (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="8b220-128">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b220-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b220-129">See Also</span></span>  
 <span data-ttu-id="8b220-130"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A></span><span class="sxs-lookup"><span data-stu-id="8b220-130"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A></span></span>   
 <span data-ttu-id="8b220-131"><xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A></span><span class="sxs-lookup"><span data-stu-id="8b220-131"><xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A></span></span>   
 <span data-ttu-id="8b220-132">[Gewusst wie: Suchen nach Unterverzeichnissen mit einem bestimmten Muster](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md) </span><span class="sxs-lookup"><span data-stu-id="8b220-132">[How to: Find Subdirectories with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md) </span></span>  
 <span data-ttu-id="8b220-133">[Problembehandlung: Lesen aus und Schreiben in Textdateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="8b220-133">[Troubleshooting: Reading from and Writing to Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md) </span></span>  
 [<span data-ttu-id="8b220-134">Gewusst wie: Abrufen einer Sammlung von Dateien in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="8b220-134">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)

