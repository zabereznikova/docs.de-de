---
title: 'Gewusst wie: Erstellen einer Kopie einer Datei im gleichen Ordner'
ms.date: 07/20/2015
f1_keywords:
- File.Copy
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: b2fdda86-e666-42c2-9706-9527e9fa68ff
ms.openlocfilehash: 741f0c80ba268369ebdd598460e9d5fa13d09571
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401679"
---
# <a name="how-to-create-a-copy-of-a-file-in-the-same-directory-in-visual-basic"></a><span data-ttu-id="87202-102">Gewusst wie: Erstellen einer Kopie einer Datei im gleichen Ordner in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="87202-102">How to: Create a Copy of a File in the Same Directory in Visual Basic</span></span>

<span data-ttu-id="87202-103">Verwenden Sie die `My.Computer.FileSystem.CopyFile`-Methode, um die Dateien zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="87202-103">Use the `My.Computer.FileSystem.CopyFile` method to copy files.</span></span> <span data-ttu-id="87202-104">Die Parameter der Methode bieten die Möglichkeit, vorhandene Dateien zu überschreiben, die Datei umzubenennen, den Fortschritt des Vorgangs anzuzeigen sowie den Benutzer zu erlauben, den Vorgang abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="87202-104">The parameters allow you to overwrite existing files, rename the file, show the progress of the operation, and allow the user to cancel the operation.</span></span>  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder"></a><span data-ttu-id="87202-105">Erstellen einer Kopie einer Datei im gleichen Ordner</span><span class="sxs-lookup"><span data-stu-id="87202-105">To create a copy of a file in the same folder</span></span>  
  
- <span data-ttu-id="87202-106">Verwenden Sie die `CopyFile`-Methode, und stellen Sie dabei die Zieldatei und den Speicherort bereit.</span><span class="sxs-lookup"><span data-stu-id="87202-106">Use the `CopyFile` method, supplying the target file and the location.</span></span> <span data-ttu-id="87202-107">Im folgenden Beispiel wird eine Kopie von `test.txt` mit dem Namen `test2.txt` erstellt.</span><span class="sxs-lookup"><span data-stu-id="87202-107">The following example creates a copy of `test.txt` called `test2.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#51)]  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder-overwriting-existing-files"></a><span data-ttu-id="87202-108">So erstellen Sie eine Kopie einer Datei im selben Ordner und überschreiben dabei vorhandene Dateien</span><span class="sxs-lookup"><span data-stu-id="87202-108">To create a copy of a file in the same folder, overwriting existing files</span></span>  
  
- <span data-ttu-id="87202-109">Verwenden Sie die `CopyFile`-Methode, stellen Sie die Zieldatei sowie den Speicherort bereit, und setzen Sie `overwrite` auf `True`.</span><span class="sxs-lookup"><span data-stu-id="87202-109">Use the `CopyFile` method, supplying the target file and location, and setting `overwrite` to `True`.</span></span> <span data-ttu-id="87202-110">Das folgende Beispiel erstellt eine Kopie von `test.txt` mit dem Namen `test2.txt` und überschreibt vorhandene Dateien mit diesem Namen.</span><span class="sxs-lookup"><span data-stu-id="87202-110">The following example creates a copy of `test.txt` called `test2.txt` and overwrites any existing files by that name.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#52)]  
  
## <a name="robust-programming"></a><span data-ttu-id="87202-111">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="87202-111">Robust Programming</span></span>  

 <span data-ttu-id="87202-112">Die folgenden Bedingungen können einen Ausnahmefehler auslösen:</span><span class="sxs-lookup"><span data-stu-id="87202-112">The following conditions may cause an exception to be thrown:</span></span>  
  
- <span data-ttu-id="87202-113">Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="87202-113">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="87202-114">Das System konnte den absoluten Pfad nicht abrufen (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="87202-114">The system could not retrieve the absolute path (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="87202-115">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="87202-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="87202-116">Die Quelldatei ist ungültig oder nicht vorhanden (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="87202-116">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="87202-117">Der kombinierte Pfad verweist auf ein vorhandenes Verzeichnis (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="87202-117">The combined path points to an existing directory (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="87202-118">Die Zieldatei ist vorhanden und `overwrite` ist auf `False` festgelegt (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="87202-118">The destination file exists and `overwrite` is set to `False` (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="87202-119">Der Benutzer hat keine ausreichende Berechtigungen für den Dateizugriff (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="87202-119">The user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="87202-120">Eine Zielordner mit dem gleichen Namen ist in Gebrauch (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="87202-120">A file in the target folder with the same name is in use (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="87202-121">Der Pfad eines Datei- oder Ordnernamens enthält einen Doppelpunkt (:) oder weist ein ungültiges Format auf (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="87202-121">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="87202-122">`ShowUI` ist auf `True` festgelegt, `onUserCancel` ist auf `ThrowException` festgelegt, und der Benutzer hat den Vorgang abgebrochen (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="87202-122">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and the user has cancelled the operation (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="87202-123">`ShowUI` ist auf `True` festgelegt, `onUserCancel` ist auf `ThrowException` festgelegt, und ein nicht angegebener E/A-Fehler tritt auf (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="87202-123">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="87202-124">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="87202-124">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="87202-125">Der Benutzer hat nicht die erforderliche Berechtigung (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="87202-125">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="87202-126">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="87202-126">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87202-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87202-127">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- [<span data-ttu-id="87202-128">Gewusst wie: Kopieren von Dateien mit einem bestimmten Muster in ein Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="87202-128">How to: Copy Files with a Specific Pattern to a Directory</span></span>](how-to-copy-files-with-a-specific-pattern-to-a-directory.md)
- [<span data-ttu-id="87202-129">Gewusst wie: Erstellen einer Kopie einer Datei in einem anderen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="87202-129">How to: Create a Copy of a File in a Different Directory</span></span>](how-to-create-a-copy-of-a-file-in-a-different-directory.md)
- [<span data-ttu-id="87202-130">Gewusst wie: Kopieren eines Verzeichnisses in ein anderes Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="87202-130">How to: Copy a Directory to Another Directory</span></span>](how-to-copy-a-directory-to-another-directory.md)
- [<span data-ttu-id="87202-131">Gewusst wie: Umbenennen einer Datei</span><span class="sxs-lookup"><span data-stu-id="87202-131">How to: Rename a File</span></span>](how-to-rename-a-file.md)
