---
title: 'Gewusst wie: Kopieren von Dateien mit einem bestimmten Muster in ein Verzeichnis'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: f205d2ad-bbe5-4d55-8a40-acda21aa82dd
ms.openlocfilehash: 7e263e2c9035db54dbb58c6c78c0647d5442504e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401705"
---
# <a name="how-to-copy-files-with-a-specific-pattern-to-a-directory-in-visual-basic"></a><span data-ttu-id="27d32-102">Gewusst wie: Kopieren von Dateien mit einem bestimmten Muster in ein Verzeichnis in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="27d32-102">How to: Copy Files with a Specific Pattern to a Directory in Visual Basic</span></span>

<span data-ttu-id="27d32-103">Die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>-Methode gibt eine schreibgeschützte Auflistung von Zeichenfolgen zurück, die die Pfadnamen für die Dateien darstellen.</span><span class="sxs-lookup"><span data-stu-id="27d32-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> method returns a read-only collection of strings representing the path names for the files.</span></span> <span data-ttu-id="27d32-104">Sie können den `wildCards` -Parameter verwenden, um ein bestimmtes Muster anzugeben.</span><span class="sxs-lookup"><span data-stu-id="27d32-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span>  
  
 <span data-ttu-id="27d32-105">Wenn keine übereinstimmenden Dateien gefunden werden, wird eine leere Auflistung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="27d32-105">An empty collection is returned if no matching files are found.</span></span>  
  
 <span data-ttu-id="27d32-106">Mit der <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> -Methode können Sie die Dateien in ein Verzeichnis kopieren.</span><span class="sxs-lookup"><span data-stu-id="27d32-106">You can use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> method to copy the files to a directory.</span></span>  
  
### <a name="to-copy-files-with-a-specific-pattern-to-a-directory"></a><span data-ttu-id="27d32-107">So kopieren Sie Dateien mit einem bestimmten Muster in ein Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="27d32-107">To copy files with a specific pattern to a directory</span></span>  
  
1. <span data-ttu-id="27d32-108">Verwenden Sie die `GetFiles` -Methode, um die Liste der Dateien zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="27d32-108">Use the `GetFiles` method to return the list of files.</span></span> <span data-ttu-id="27d32-109">In diesem Beispiel werden alle RTF-Dateien im angegebenen Verzeichnis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="27d32-109">This example returns all .rtf files in the specified directory.</span></span>  
  
     [!code-vb[VbFileIOMisc#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#36)]  
  
2. <span data-ttu-id="27d32-110">Verwenden Sie die `CopyFile` -Methode, um die Dateien zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="27d32-110">Use the `CopyFile` method to copy the files.</span></span> <span data-ttu-id="27d32-111">In diesem Beispiel werden die Dateien in das Verzeichnis `testdirectory`kopiert.</span><span class="sxs-lookup"><span data-stu-id="27d32-111">This example copies the files to the directory named `testdirectory`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#88)]  
  
3. <span data-ttu-id="27d32-112">Schließen Sie die `For` -Anweisung mit einer `Next` -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="27d32-112">Close the `For` statement with a `Next` statement.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#89)]  
  
## <a name="example"></a><span data-ttu-id="27d32-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="27d32-113">Example</span></span>  

 <span data-ttu-id="27d32-114">Im folgenden Beispiel, das der vollständigen Fassung der oben aufgeführten Codeausschnitte entspricht, werden alle RTF-Dateien im angegebenen Verzeichnis in das Verzeichnis `testdirectory`kopiert.</span><span class="sxs-lookup"><span data-stu-id="27d32-114">The following example, which presents the above snippets in complete form, copies all .rtf files in the specified directory to the directory named `testdirectory`.</span></span>  
  
 [!code-vb[VbFileIOMisc#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#37)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="27d32-115">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="27d32-115">.NET Framework Security</span></span>  

 <span data-ttu-id="27d32-116">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="27d32-116">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="27d32-117">Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="27d32-117">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="27d32-118">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="27d32-118">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="27d32-119">Das Verzeichnis ist nicht vorhanden (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="27d32-119">The directory does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
- <span data-ttu-id="27d32-120">Das Verzeichnis verweist auf eine vorhandene Datei (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="27d32-120">The directory points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="27d32-121">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="27d32-121">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="27d32-122">Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="27d32-122">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="27d32-123">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="27d32-123">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span> <span data-ttu-id="27d32-124">Der Benutzer verfügt nicht über die erforderlichen Berechtigungen (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="27d32-124">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d32-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27d32-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>
- [<span data-ttu-id="27d32-126">Gewusst wie: Suchen nach Unterverzeichnissen mit einem bestimmten Muster</span><span class="sxs-lookup"><span data-stu-id="27d32-126">How to: Find Subdirectories with a Specific Pattern</span></span>](how-to-find-subdirectories-with-a-specific-pattern.md)
- [<span data-ttu-id="27d32-127">Problembehandlung: Lesen aus und Schreiben in Textdateien</span><span class="sxs-lookup"><span data-stu-id="27d32-127">Troubleshooting: Reading from and Writing to Text Files</span></span>](troubleshooting-reading-from-and-writing-to-text-files.md)
- [<span data-ttu-id="27d32-128">Gewusst wie: Abrufen einer Sammlung von Dateien in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="27d32-128">How to: Get the Collection of Files in a Directory</span></span>](how-to-get-the-collection-of-files-in-a-directory.md)
