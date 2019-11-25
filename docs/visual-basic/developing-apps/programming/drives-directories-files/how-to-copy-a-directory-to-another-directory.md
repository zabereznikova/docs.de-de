---
title: 'Vorgehensweise: Kopieren eines Verzeichnisses in ein anderes Verzeichnis'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], copying directories
- I/O [Visual Basic], copying folders
- folders [Visual Basic], copying
- directories [Visual Basic], copying
ms.assetid: 2a370bd7-10ba-4219-afc4-4519d031eb6c
ms.openlocfilehash: a23079f093f53ab8e20eb71c684a594dcf7f894b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348865"
---
# <a name="how-to-copy-a-directory-to-another-directory-in-visual-basic"></a><span data-ttu-id="5f847-102">Vorgehensweise: Kopieren eines Verzeichnisses in ein anderes Verzeichnis in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5f847-102">How to: Copy a Directory to Another Directory in Visual Basic</span></span>

<span data-ttu-id="5f847-103">Verwenden Sie die <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A>-Methode zum Kopieren eines Verzeichnisses in ein anderes Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5f847-103">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> method to copy a directory to another directory.</span></span> <span data-ttu-id="5f847-104">Diese Methode kopiert den Inhalt des Verzeichnisses sowie das Verzeichnis selbst.</span><span class="sxs-lookup"><span data-stu-id="5f847-104">This method copies the contents of the directory as well as the directory itself.</span></span> <span data-ttu-id="5f847-105">Wenn das Zielverzeichnis nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="5f847-105">If the target directory does not exist, it will be created.</span></span> <span data-ttu-id="5f847-106">Wenn ein Verzeichnis mit dem gleichen Namen am Zielspeicherort vorhanden ist und `overwrite` auf `False` festgelegt ist, werden die Inhalte der beiden Verzeichnisse zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="5f847-106">If a directory with the same name exists in the target location and `overwrite` is set to `False`, the contents of the two directories will be merged.</span></span> <span data-ttu-id="5f847-107">Sie können während des Vorgangs einen neuen Namen für das Verzeichnis angeben.</span><span class="sxs-lookup"><span data-stu-id="5f847-107">You can specify a new name for the directory during the operation.</span></span>

<span data-ttu-id="5f847-108">Beim Kopieren von Dateien innerhalb eines Verzeichnisses können Ausnahmen ausgelöst werden, die durch eine bestimmte Datei verursacht werden. Dies kann zum Beispiel eine Datei sein, die während einer Zusammenführung vorhanden ist, wenn `overwrite` auf `False` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5f847-108">When copying files within a directory, exceptions may be thrown that are caused by specific file, such as a file existing during a merge while `overwrite` is set to `False`.</span></span> <span data-ttu-id="5f847-109">Wenn solche Ausnahmen ausgelöst werden, werden sie zu einer einzigen Ausnahme konsolidiert, deren `Data`-Eigenschaft Einträge enthält, in denen der Datei- oder Verzeichnispfad der Schlüssel ist und die spezifische Ausnahmemeldung im entsprechenden Wert enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="5f847-109">When such exceptions are thrown, they are consolidated into a single exception, whose `Data` property holds entries in which the file or directory path is the key and the specific exception message is contained in the corresponding value.</span></span>

## <a name="to-copy-a-directory-to-another-directory"></a><span data-ttu-id="5f847-110">Kopieren eines Verzeichnisses in ein anderes Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="5f847-110">To copy a directory to another directory</span></span>

- <span data-ttu-id="5f847-111">Verwenden Sie die `CopyDirectory`-Methode, um Verzeichnisnamen von Quelle und Ziel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5f847-111">Use the `CopyDirectory` method, specifying source and destination directory names.</span></span> <span data-ttu-id="5f847-112">Im folgenden Beispiel wird das Verzeichnis mit dem Namen `TestDirectory1` in `TestDirectory2` kopiert, wobei vorhandene Dateien überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="5f847-112">The following example copies the directory named `TestDirectory1` into `TestDirectory2`, overwriting existing files.</span></span>

    [!code-vb[VbVbcnMyFileSystem#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#16)]

    <span data-ttu-id="5f847-113">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5f847-113">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="5f847-114">In der Codeausschnittauswahl befindet es sich unter **Dateisystem – Verarbeiten von Laufwerken, Ordnern und Dateien**.</span><span class="sxs-lookup"><span data-stu-id="5f847-114">In the code snippet picker, it is located in **File system - Processing Drives, Folders, and Files**.</span></span> <span data-ttu-id="5f847-115">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="5f847-115">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>

## <a name="robust-programming"></a><span data-ttu-id="5f847-116">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="5f847-116">Robust Programming</span></span>

<span data-ttu-id="5f847-117">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="5f847-117">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="5f847-118">Der neue Name, der für das Verzeichnis angegeben wird, enthält einen Doppelpunkt (:) oder einen Schrägstrich (\ oder /) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="5f847-118">The new name specified for the directory contains a colon (:) or slash (\ or /) (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="5f847-119">Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="5f847-119">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="5f847-120">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="5f847-120">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="5f847-121">`destinationDirectoryName` ist `Nothing` oder eine leere Zeichenfolge (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="5f847-121">`destinationDirectoryName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>)</span></span>

- <span data-ttu-id="5f847-122">Das Quellverzeichnis ist nicht vorhanden (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="5f847-122">The source directory does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>

- <span data-ttu-id="5f847-123">Das Quellverzeichnis ist ein Stammverzeichnis (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="5f847-123">The source directory is a root directory (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="5f847-124">Der kombinierte Pfad verweist auf eine vorhandene Datei (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="5f847-124">The combined path points to an existing file (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="5f847-125">Der Quellpfad und der Zielpfad sind identisch (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="5f847-125">The source path and target path are the same (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="5f847-126">`ShowUI` ist auf `UIOption.AllDialogs` festgelegt, und der Benutzer bricht den Vorgang ab, oder eine oder mehrere Dateien im Verzeichnis können nicht kopiert werden (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="5f847-126">`ShowUI` is set to `UIOption.AllDialogs` and the user cancels the operation, or one or more files in the directory cannot be copied (<xref:System.OperationCanceledException>).</span></span>

- <span data-ttu-id="5f847-127">Der Vorgang ist zyklisch (<xref:System.InvalidOperationException>).</span><span class="sxs-lookup"><span data-stu-id="5f847-127">The operation is cyclic (<xref:System.InvalidOperationException>).</span></span>

- <span data-ttu-id="5f847-128">Der Pfad enthält einen Doppelpunkt (:) (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="5f847-128">The path contains a colon (:) (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="5f847-129">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="5f847-129">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>

- <span data-ttu-id="5f847-130">Der Pfad eines Datei- oder Ordnernamens enthält einen Doppelpunkt (:) oder weist ein ungültiges Format auf (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="5f847-130">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="5f847-131">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="5f847-131">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>

- <span data-ttu-id="5f847-132">Eine Zieldatei ist vorhanden, aber nicht zugänglich (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="5f847-132">A destination file exists but cannot be accessed (<xref:System.UnauthorizedAccessException>).</span></span>

## <a name="see-also"></a><span data-ttu-id="5f847-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f847-133">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A>
- [<span data-ttu-id="5f847-134">Vorgehensweise: Suchen nach Unterverzeichnissen mit einem bestimmten Muster</span><span class="sxs-lookup"><span data-stu-id="5f847-134">How to: Find Subdirectories with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)
- [<span data-ttu-id="5f847-135">Vorgehensweise: Abrufen einer Auflistung der Dateien in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="5f847-135">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
