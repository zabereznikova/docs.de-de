---
title: 'Gewusst wie: Umbenennen einer Datei'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], renaming files
- files [Visual Basic], renaming
ms.assetid: 0ea7e0c8-2cb2-4bf5-a00d-7b6e3c08a3bc
ms.openlocfilehash: 3de41ee6627315f0e26964b75f564ff98fe472ec
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411589"
---
# <a name="how-to-rename-a-file-in-visual-basic"></a><span data-ttu-id="86019-102">Gewusst wie: Umbenennen einer Datei in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="86019-102">How to: Rename a File in Visual Basic</span></span>

<span data-ttu-id="86019-103">Verwenden Sie die `RenameFile`-Methode des `My.Computer.FileSystem`-Objekts, um eine Datei umzubenennen, indem Sie den aktuellen Standort, Dateinamen sowie den neuen Dateinamen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="86019-103">Use the `RenameFile` method of the `My.Computer.FileSystem` object to rename a file by supplying the current location, file name, and the new file name.</span></span> <span data-ttu-id="86019-104">Diese Methode kann nicht dazu verwendet werden, um eine Datei zu verschieben; verwenden Sie die `MoveFile`-Methode, um die Datei zu verschieben und umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="86019-104">This method cannot be used to move a file; use the `MoveFile` method to move and rename the file.</span></span>  
  
### <a name="to-rename-a-file"></a><span data-ttu-id="86019-105">So benennen Sie eine Datei um</span><span class="sxs-lookup"><span data-stu-id="86019-105">To rename a file</span></span>  
  
- <span data-ttu-id="86019-106">Verwenden Sie die `My.Computer.FileSystem.RenameFile`-Methode, um eine Datei umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="86019-106">Use the `My.Computer.FileSystem.RenameFile` method to rename a file.</span></span> <span data-ttu-id="86019-107">In diesem Beispiel wird die Datei `Test.txt` in `SecondTest.txt` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="86019-107">This example renames the file named `Test.txt` to `SecondTest.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#9)]  
  
 <span data-ttu-id="86019-108">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="86019-108">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="86019-109">In der Codeausschnittauswahl befindet sich der Ausschnitt unter **Dateisystem - Verarbeiten von Laufwerken, Ordnern und Dateien**.</span><span class="sxs-lookup"><span data-stu-id="86019-109">In the code snippet picker, the snippet is located in **File system - Processing Drives, Folders, and Files**.</span></span> <span data-ttu-id="86019-110">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="86019-110">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="86019-111">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="86019-111">Robust Programming</span></span>  

 <span data-ttu-id="86019-112">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="86019-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="86019-113">Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="86019-113">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="86019-114">`newName` enthält Pfadinformationen (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="86019-114">`newName` contains path information (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="86019-115">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="86019-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="86019-116">`newName` ist `Nothing` oder eine leere Zeichenfolge (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="86019-116">`newName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="86019-117">Die Quelldatei ist ungültig oder nicht vorhanden (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="86019-117">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="86019-118">Eine Datei oder ein Verzeichnis mit dem in `newName` angegebenen Namen (<xref:System.IO.IOException>) ist bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="86019-118">There is an existing file or directory with the name specified in `newName` (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="86019-119">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="86019-119">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="86019-120">Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="86019-120">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="86019-121">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="86019-121">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="86019-122">Der Benutzer hat nicht die erforderliche Berechtigung (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="86019-122">The user does not have the required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86019-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86019-123">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A>
- [<span data-ttu-id="86019-124">Gewusst wie: Verschieben einer Datei</span><span class="sxs-lookup"><span data-stu-id="86019-124">How to: Move a File</span></span>](how-to-move-a-file.md)
- [<span data-ttu-id="86019-125">Erstellen, Löschen und Verschieben von Dateien und Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="86019-125">Creating, Deleting, and Moving Files and Directories</span></span>](creating-deleting-and-moving-files-and-directories.md)
- [<span data-ttu-id="86019-126">Gewusst wie: Erstellen einer Kopie einer Datei im gleichen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="86019-126">How to: Create a Copy of a File in the Same Directory</span></span>](how-to-create-a-copy-of-a-file-in-the-same-directory.md)
- [<span data-ttu-id="86019-127">Gewusst wie: Erstellen einer Kopie einer Datei in einem anderen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="86019-127">How to: Create a Copy of a File in a Different Directory</span></span>](how-to-create-a-copy-of-a-file-in-a-different-directory.md)
