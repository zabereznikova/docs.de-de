---
title: 'Gewusst wie: Erstellen einer Kopie einer Datei in einem anderen Verzeichnis'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: 88e2145c-d414-45a5-ad03-6f5d58ecca26
ms.openlocfilehash: 3b4b41e105d6bb6a17fbb688aa4718b33c23b9d6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401692"
---
# <a name="how-to-create-a-copy-of-a-file-in-a-different-directory-in-visual-basic"></a><span data-ttu-id="b8dca-102">Gewusst wie: Erstellen einer Kopie einer Datei in einem anderen Verzeichnis in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8dca-102">How to: Create a Copy of a File in a Different Directory in Visual Basic</span></span>

<span data-ttu-id="b8dca-103">Mit der `My.Computer.FileSystem.CopyFile`-Methode können Sie Dateien kopieren.</span><span class="sxs-lookup"><span data-stu-id="b8dca-103">The `My.Computer.FileSystem.CopyFile` method allows you to copy files.</span></span> <span data-ttu-id="b8dca-104">Die Parameter der Methode bieten die Möglichkeit, vorhandene Dateien zu überschreiben, die Datei umzubenennen, den Fortschritt des Vorgangs anzuzeigen sowie den Benutzer zu erlauben, den Vorgang abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="b8dca-104">Its parameters provide the ability to overwrite existing files, rename the file, show the progress of the operation, and allow the user to cancel the operation.</span></span>  
  
### <a name="to-copy-a-text-file-to-another-folder"></a><span data-ttu-id="b8dca-105">So kopieren Sie eine Textdatei in einen anderen Ordner</span><span class="sxs-lookup"><span data-stu-id="b8dca-105">To copy a text file to another folder</span></span>  
  
- <span data-ttu-id="b8dca-106">Verwenden Sie die `CopyFile`-Methode zum Kopieren einer Datei, und geben Sie eine Quelldatei sowie das Zielverzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="b8dca-106">Use the `CopyFile` method to copy a file, specifying a source file and the target directory.</span></span> <span data-ttu-id="b8dca-107">Mit dem `overwrite`-Parameter können Sie angeben, ob vorhandene Dateien überschrieben werden sollen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="b8dca-107">The `overwrite` parameter allows you to specify whether or not to overwrite existing files.</span></span> <span data-ttu-id="b8dca-108">In den folgenden Codebeispielen wird veranschaulicht, wie `CopyFile` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8dca-108">The following code examples demonstrate how to use `CopyFile`.</span></span>  
  
     [!code-vb[VbFileIOMisc#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#24)]  
  
## <a name="robust-programming"></a><span data-ttu-id="b8dca-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="b8dca-109">Robust Programming</span></span>  

 <span data-ttu-id="b8dca-110">Die folgenden Bedingungen können einen Ausnahmefehler auslösen:</span><span class="sxs-lookup"><span data-stu-id="b8dca-110">The following conditions may cause an exception to be thrown:</span></span>  
  
- <span data-ttu-id="b8dca-111">Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="b8dca-111">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="b8dca-112">Das System konnte den absoluten Pfad nicht abrufen (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="b8dca-112">The system could not retrieve the absolute path (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="b8dca-113">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="b8dca-113">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="b8dca-114">Die Quelldatei ist ungültig oder nicht vorhanden (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="b8dca-114">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="b8dca-115">Der kombinierte Pfad verweist auf ein vorhandenes Verzeichnis (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="b8dca-115">The combined path points to an existing directory (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="b8dca-116">Die Zieldatei ist vorhanden und `overwrite` ist auf `False` festgelegt (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="b8dca-116">The destination file exists and `overwrite` is set to `False` (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="b8dca-117">Der Benutzer hat keine ausreichende Berechtigungen für den Dateizugriff (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="b8dca-117">The user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="b8dca-118">Eine Zielordner mit dem gleichen Namen ist in Gebrauch (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="b8dca-118">A file in the target folder with the same name is in use (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="b8dca-119">Der Pfad eines Datei- oder Ordnernamens enthält einen Doppelpunkt (:) oder weist ein ungültiges Format auf (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="b8dca-119">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="b8dca-120">`ShowUI` ist auf `True` festgelegt, `onUserCancel` ist auf `ThrowException` festgelegt, und der Benutzer hat den Vorgang abgebrochen (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="b8dca-120">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and the user has cancelled the operation (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="b8dca-121">`ShowUI` ist auf `True` festgelegt, `onUserCancel` ist auf `ThrowException` festgelegt, und ein nicht angegebener E/A-Fehler tritt auf (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="b8dca-121">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="b8dca-122">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="b8dca-122">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="b8dca-123">Der Benutzer hat nicht die erforderliche Berechtigung (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="b8dca-123">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="b8dca-124">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="b8dca-124">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8dca-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b8dca-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- [<span data-ttu-id="b8dca-126">Gewusst wie: Kopieren von Dateien mit einem bestimmten Muster in ein Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="b8dca-126">How to: Copy Files with a Specific Pattern to a Directory</span></span>](how-to-copy-files-with-a-specific-pattern-to-a-directory.md)
- [<span data-ttu-id="b8dca-127">Gewusst wie: Erstellen einer Kopie einer Datei im gleichen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="b8dca-127">How to: Create a Copy of a File in the Same Directory</span></span>](how-to-create-a-copy-of-a-file-in-the-same-directory.md)
- [<span data-ttu-id="b8dca-128">Gewusst wie: Kopieren eines Verzeichnisses in ein anderes Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="b8dca-128">How to: Copy a Directory to Another Directory</span></span>](how-to-copy-a-directory-to-another-directory.md)
- [<span data-ttu-id="b8dca-129">Gewusst wie: Umbenennen einer Datei</span><span class="sxs-lookup"><span data-stu-id="b8dca-129">How to: Rename a File</span></span>](how-to-rename-a-file.md)
