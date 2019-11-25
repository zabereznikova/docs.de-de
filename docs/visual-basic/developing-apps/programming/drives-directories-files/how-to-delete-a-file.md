---
title: 'Vorgehensweise: Löschen einer Datei'
ms.date: 07/20/2015
helpviewer_keywords:
- Delete method [Visual Basic]
- files [Visual Basic], deleting
- files [Visual Basic], manipulating
- File object
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
ms.openlocfilehash: 57182f1a1d92b7fe954fd26b32c5e4b1107823ee
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348779"
---
# <a name="how-to-delete-a-file-in-visual-basic"></a><span data-ttu-id="e3aa8-102">Vorgehensweise: Löschen einer Datei in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e3aa8-102">How to: Delete a File in Visual Basic</span></span>

<span data-ttu-id="e3aa8-103">Die `DeleteFile`-Methode des `My.Computer.FileSystem`-Objekts ermöglicht das Löschen einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="e3aa8-103">The `DeleteFile` method of the `My.Computer.FileSystem` object allows you to delete a file.</span></span> <span data-ttu-id="e3aa8-104">Sie bietet u.a. folgende Optionen: ob die gelöschte Datei in den **Papierkorb** verschoben werden soll, ob der Benutzer den Löschvorgang bestätigen muss und was passiert, wenn der Benutzer den Vorgang abbricht.</span><span class="sxs-lookup"><span data-stu-id="e3aa8-104">Among the options it offers are: whether to send the deleted file to the **Recycle Bin**, whether to ask the user to confirm that the file should be deleted, and what to do when the user cancels the operation.</span></span>  
  
### <a name="to-delete-a-text-file"></a><span data-ttu-id="e3aa8-105">Löschen einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="e3aa8-105">To delete a text file</span></span>  
  
- <span data-ttu-id="e3aa8-106">Verwenden Sie die `DeleteFile`-Methode zum Löschen der Datei.</span><span class="sxs-lookup"><span data-stu-id="e3aa8-106">Use the `DeleteFile` method to delete the file.</span></span> <span data-ttu-id="e3aa8-107">Der folgende Code veranschaulicht, wie Sie die Datei mit dem Namen `test.txt` löschen können.</span><span class="sxs-lookup"><span data-stu-id="e3aa8-107">The following code demonstrates how to delete the file named `test.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#22)]  
  
### <a name="to-delete-a-text-file-and-ask-the-user-to-confirm-that-the-file-should-be-deleted"></a><span data-ttu-id="e3aa8-108">Löschen einer Textdatei und Bestätigen des Löschvorgangs der Datei durch den Benutzer</span><span class="sxs-lookup"><span data-stu-id="e3aa8-108">To delete a text file and ask the user to confirm that the file should be deleted</span></span>  
  
- <span data-ttu-id="e3aa8-109">Verwenden Sie die `DeleteFile`-Methode zum Löschen der Datei, und legen Sie `showUI` auf `AllDialogs` fest.</span><span class="sxs-lookup"><span data-stu-id="e3aa8-109">Use the `DeleteFile` method to delete the file, setting `showUI` to `AllDialogs`.</span></span> <span data-ttu-id="e3aa8-110">Der folgende Code veranschaulicht, wie Sie die Datei mit dem Namen `test.txt` löschen können, und wie Sie dem Benutzer das Bestätigen des Löschvorgangs ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e3aa8-110">The following code demonstrates how to delete the file named `test.txt` and allow the user to confirm that the file should be deleted.</span></span>  
  
     [!code-vb[VbFileIOMisc#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#9)]  
  
### <a name="to-delete-a-text-file-and-send-it-to-the-recycle-bin"></a><span data-ttu-id="e3aa8-111">Löschen einer Textdatei und anschließendes Verschieben in den Papierkorb</span><span class="sxs-lookup"><span data-stu-id="e3aa8-111">To delete a text file and send it to the Recycle Bin</span></span>  
  
- <span data-ttu-id="e3aa8-112">Verwenden Sie die `DeleteFile`-Methode, um die Datei zu löschen, und geben Sie `SendToRecycleBin` für den `recycle`-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="e3aa8-112">Use the `DeleteFile` method to delete the file, specifying `SendToRecycleBin` for the `recycle` parameter.</span></span> <span data-ttu-id="e3aa8-113">Der folgende Code veranschaulicht, wie Sie die Datei mit dem Namen `test.txt` löschen und sie in den **Papierkorb** verschieben können.</span><span class="sxs-lookup"><span data-stu-id="e3aa8-113">The following code demonstrates how to delete the file named `test.txt` and send it to the **Recycle Bin**.</span></span>  
  
     [!code-vb[VbFileIOMisc#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#10)]  
  
## <a name="robust-programming"></a><span data-ttu-id="e3aa8-114">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="e3aa8-114">Robust Programming</span></span>  

 <span data-ttu-id="e3aa8-115">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="e3aa8-115">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="e3aa8-116">Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="e3aa8-116">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="e3aa8-117">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="e3aa8-117">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="e3aa8-118">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="e3aa8-118">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="e3aa8-119">Der Pfad eines Datei- oder Ordnernamens enthält einen Doppelpunkt (:) oder weist ein ungültiges Format auf (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="e3aa8-119">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="e3aa8-120">Die Datei wird gerade verwendet (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="e3aa8-120">The file is in use (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="e3aa8-121">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="e3aa8-121">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="e3aa8-122">Die Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="e3aa8-122">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="e3aa8-123">Der Benutzer verfügt nicht über die nötigen Berechtigungen, um die Datei zu löschen, oder die Datei ist schreibgeschützt (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="e3aa8-123">The user does not have permission to delete the file, or the file is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="e3aa8-124">Ein teilweise vertrauenswürdiger Kontext, in dem der Benutzer nicht über ausreichende Berechtigungen für den Dateizugriff verfügt (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="e3aa8-124">A partial-trust situation exists in which the user does not have sufficient permissions (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="e3aa8-125">Der Benutzer hat den Vorgang abgebrochen, und `onUserCancel` wird auf `ThrowException` festgelegt (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="e3aa8-125">The user cancelled the operation and `onUserCancel` is set to `ThrowException` (<xref:System.OperationCanceledException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3aa8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3aa8-126">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.UIOption>
- <xref:Microsoft.VisualBasic.FileIO.RecycleOption>
- [<span data-ttu-id="e3aa8-127">Vorgehensweise: Abrufen einer Auflistung der Dateien in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="e3aa8-127">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
