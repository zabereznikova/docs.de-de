---
title: 'Gewusst wie: Umbenennen einer Datei in Visual Basic'
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
- I/O [Visual Basic], renaming files
- files, renaming
ms.assetid: 0ea7e0c8-2cb2-4bf5-a00d-7b6e3c08a3bc
caps.latest.revision: 21
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
ms.openlocfilehash: f003cfc7c7880a47515f7328a0503072f3b02cbf
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-rename-a-file-in-visual-basic"></a><span data-ttu-id="dbc40-102">Gewusst wie: Umbenennen einer Datei in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dbc40-102">How to: Rename a File in Visual Basic</span></span>
<span data-ttu-id="dbc40-103">Verwenden Sie die `RenameFile`-Methode des `My.Computer.FileSystem`-Objekts, um eine Datei umzubenennen, indem Sie den aktuellen Standort, Dateinamen sowie den neuen Dateinamen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="dbc40-103">Use the `RenameFile` method of the `My.Computer.FileSystem` object to rename a file by supplying the current location, file name, and the new file name.</span></span> <span data-ttu-id="dbc40-104">Diese Methode kann nicht dazu verwendet werden, um eine Datei zu verschieben; verwenden Sie die `MoveFile`-Methode, um die Datei zu verschieben und umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="dbc40-104">This method cannot be used to move a file; use the `MoveFile` method to move and rename the file.</span></span>  
  
### <a name="to-rename-a-file"></a><span data-ttu-id="dbc40-105">So benennen Sie eine Datei um</span><span class="sxs-lookup"><span data-stu-id="dbc40-105">To rename a file</span></span>  
  
-   <span data-ttu-id="dbc40-106">Verwenden Sie die `My.Computer.FileSystem.RenameFile`-Methode, um eine Datei umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="dbc40-106">Use the `My.Computer.FileSystem.RenameFile` method to rename a file.</span></span> <span data-ttu-id="dbc40-107">In diesem Beispiel wird die Datei `Test.txt` in `SecondTest.txt` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="dbc40-107">This example renames the file named `Test.txt` to `SecondTest.txt`.</span></span>  
  
     <span data-ttu-id="dbc40-108">[!code-vb[VbVbcnMyFileSystem#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-rename-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="dbc40-108">[!code-vb[VbVbcnMyFileSystem#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-rename-a-file_1.vb)]</span></span>  
  
 <span data-ttu-id="dbc40-109">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dbc40-109">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="dbc40-110">In der Codeausschnittauswahl befindet sich der Ausschnitt unter **Dateisystem - Verarbeiten von Laufwerken, Ordnern und Dateien**.</span><span class="sxs-lookup"><span data-stu-id="dbc40-110">In the code snippet picker, the snippet is located in **File system - Processing Drives, Folders, and Files**.</span></span> <span data-ttu-id="dbc40-111">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="dbc40-111">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="dbc40-112">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="dbc40-112">Robust Programming</span></span>  
 <span data-ttu-id="dbc40-113">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="dbc40-113">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="dbc40-114">Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="dbc40-114">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="dbc40-115">`newName` enthält Pfadinformationen (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="dbc40-115">`newName` contains path information (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="dbc40-116">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="dbc40-116">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="dbc40-117">`newName` ist `Nothing` oder eine leere Zeichenfolge (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="dbc40-117">`newName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="dbc40-118">Die Quelldatei ist ungültig oder nicht vorhanden (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="dbc40-118">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="dbc40-119">Eine Datei oder ein Verzeichnis mit dem in `newName` angegebenen Namen (<xref:System.IO.IOException>) ist bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="dbc40-119">There is an existing file or directory with the name specified in `newName` (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="dbc40-120">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="dbc40-120">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="dbc40-121">Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="dbc40-121">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="dbc40-122">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="dbc40-122">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="dbc40-123">Der Benutzer hat nicht die erforderliche Berechtigung (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="dbc40-123">The user does not have the required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbc40-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbc40-124">See Also</span></span>  
 <span data-ttu-id="dbc40-125"><xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A></span><span class="sxs-lookup"><span data-stu-id="dbc40-125"><xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A></span></span>   
 <span data-ttu-id="dbc40-126">[Gewusst wie: Verschieben einer Datei](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-move-a-file.md) </span><span class="sxs-lookup"><span data-stu-id="dbc40-126">[How to: Move a File](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-move-a-file.md) </span></span>  
 <span data-ttu-id="dbc40-127">[Erstellen, Löschen und Verschieben von Dateien und Verzeichnissen](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md) </span><span class="sxs-lookup"><span data-stu-id="dbc40-127">[Creating, Deleting, and Moving Files and Directories](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md) </span></span>  
 <span data-ttu-id="dbc40-128">[Gewusst wie: Erstellen einer Kopie einer Datei im gleichen Verzeichnis](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md) </span><span class="sxs-lookup"><span data-stu-id="dbc40-128">[How to: Create a Copy of a File in the Same Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md) </span></span>  
 [<span data-ttu-id="dbc40-129">Gewusst wie: Erstellen einer Kopie einer Datei in einem anderen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="dbc40-129">How to: Create a Copy of a File in a Different Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)

