---
title: 'Vorgehensweise: Verschieben einer Datei'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], moving
ms.assetid: 53a7457b-5815-41ad-b37d-28537c1fb77a
ms.openlocfilehash: 29c64a7a81028d47bf489212e6d8faec5e8dda75
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335361"
---
# <a name="how-to-move-a-file-in-visual-basic"></a><span data-ttu-id="30c35-102">Vorgehensweise: Verschieben von Dateien in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="30c35-102">How to: Move a File in Visual Basic</span></span>

<span data-ttu-id="30c35-103">Mit der `My.Computer.FileSystem.MoveFile` -Methode kann eine Datei in einen anderen Ordner verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="30c35-103">The `My.Computer.FileSystem.MoveFile` method can be used to move a file to another folder.</span></span> <span data-ttu-id="30c35-104">Wenn die Zielstruktur nicht vorhanden ist, wird sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="30c35-104">If the target structure does not exist, it will be created.</span></span>  
  
### <a name="to-move-a-file"></a><span data-ttu-id="30c35-105">So verschieben Sie eine Datei</span><span class="sxs-lookup"><span data-stu-id="30c35-105">To move a file</span></span>  
  
- <span data-ttu-id="30c35-106">Verwenden Sie zum Verschieben der Datei die `MoveFile` -Methode,wobei Sie sowohl für die Quelldatei als auch für die Zieldatei deren Namen und Speicherort angeben.</span><span class="sxs-lookup"><span data-stu-id="30c35-106">Use the `MoveFile` method to move the file, specifying the file name and location for both the source file and the target file.</span></span> <span data-ttu-id="30c35-107">In diesem Beispiel wird die Datei `test.txt` aus `TestDir1` in `TestDir2`verschoben.</span><span class="sxs-lookup"><span data-stu-id="30c35-107">This example moves the file named `test.txt` from `TestDir1` to `TestDir2`.</span></span> <span data-ttu-id="30c35-108">Beachten Sie, dass der Name der Zieldatei angegeben ist, obwohl er mit dem Namen der Quelldatei identisch ist.</span><span class="sxs-lookup"><span data-stu-id="30c35-108">Note that the target file name is specified even though it is the same as the source file name.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#24)]  
  
### <a name="to-move-a-file-and-rename-it"></a><span data-ttu-id="30c35-109">So verschieben Sie eine Datei und benennen diese um</span><span class="sxs-lookup"><span data-stu-id="30c35-109">To move a file and rename it</span></span>  
  
- <span data-ttu-id="30c35-110">Verwenden Sie zum Verschieben der Datei die `MoveFile` -Methode, wobei Sie den Namen und den Speicherort der Quelldatei, den Zielspeicherort sowie den neuen Namen angeben, der am Zielspeicherort verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="30c35-110">Use the `MoveFile` method to move the file, specifying the source file name and location, the target location, and the new name at the target location.</span></span> <span data-ttu-id="30c35-111">In diesem Beispiel wird die Datei `test.txt` aus `TestDir1` in `TestDir2` verschoben und in `nexttest.txt`umbenannt.</span><span class="sxs-lookup"><span data-stu-id="30c35-111">This example moves the file named `test.txt` from `TestDir1` to `TestDir2` and renames it `nexttest.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#25)]  
  
## <a name="robust-programming"></a><span data-ttu-id="30c35-112">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="30c35-112">Robust Programming</span></span>  

 <span data-ttu-id="30c35-113">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="30c35-113">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="30c35-114">Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="30c35-114">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="30c35-115">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="30c35-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="30c35-116">`destinationFileName` ist `Nothing` oder eine leere Zeichenfolge (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="30c35-116">`destinationFileName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="30c35-117">Die Quelldatei ist ungültig oder nicht vorhanden (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="30c35-117">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="30c35-118">Der kombinierte Pfad zeigt auf ein vorhandenes Verzeichnis, die Zieldatei ist vorhanden, und `overwrite` ist auf `False`festgelegt, eine Datei im Zielverzeichnis mit demselben Namen wird derzeit verwendet, oder der Benutzer hat keine ausreichenden Berechtigungen, um auf die Datei zuzugreifen (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="30c35-118">The combined path points to an existing directory, the destination file exists and `overwrite` is set to `False`, a file in the target directory with the same name is in use, or the user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="30c35-119">Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="30c35-119">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="30c35-120">`showUI` ist auf `True`festgelegt, `onUserCancel` ist auf `ThrowException`festgelegt, und entweder der Benutzer hat den Vorgang abgebrochen, oder es tritt ein nicht näher angegebener E/A-Fehler auf (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="30c35-120">`showUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and either the user has cancelled the operation or an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="30c35-121">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="30c35-121">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="30c35-122">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="30c35-122">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="30c35-123">Der Benutzer verfügt nicht über die erforderliche Berechtigung (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="30c35-123">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c35-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30c35-124">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.MoveFile%2A>
- [<span data-ttu-id="30c35-125">Vorgehensweise: Umbenennen einer Datei</span><span class="sxs-lookup"><span data-stu-id="30c35-125">How to: Rename a File</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
- [<span data-ttu-id="30c35-126">Vorgehensweise: Erstellen einer Kopie einer Datei in einem anderen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="30c35-126">How to: Create a Copy of a File in a Different Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)
- [<span data-ttu-id="30c35-127">Vorgehensweise: Analysieren von Dateipfaden</span><span class="sxs-lookup"><span data-stu-id="30c35-127">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
