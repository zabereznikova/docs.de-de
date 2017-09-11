---
title: "Gewusst wie: Löschen einer Datei in Visual Basic"
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
- Delete method
- files, deleting
- files, manipulating
- File object
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
caps.latest.revision: 24
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
ms.openlocfilehash: e4b0b87fd403556777e0ab5a1edd517687360374
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-delete-a-file-in-visual-basic"></a><span data-ttu-id="2a4f2-102">Gewusst wie: Löschen einer Datei in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2a4f2-102">How to: Delete a File in Visual Basic</span></span>
<span data-ttu-id="2a4f2-103">Die `DeleteFile`-Methode des `My.Computer.FileSystem`-Objekts ermöglicht das Löschen einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="2a4f2-103">The `DeleteFile` method of the `My.Computer.FileSystem` object allows you to delete a file.</span></span> <span data-ttu-id="2a4f2-104">Sie bietet u.a. folgende Optionen: ob die gelöschte Datei in den **Papierkorb** verschoben werden soll, ob der Benutzer den Löschvorgang bestätigen muss und was passiert, wenn der Benutzer den Vorgang abbricht.</span><span class="sxs-lookup"><span data-stu-id="2a4f2-104">Among the options it offers are: whether to send the deleted file to the **Recycle Bin**, whether to ask the user to confirm that the file should be deleted, and what to do when the user cancels the operation.</span></span>  
  
### <a name="to-delete-a-text-file"></a><span data-ttu-id="2a4f2-105">Löschen einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="2a4f2-105">To delete a text file</span></span>  
  
-   <span data-ttu-id="2a4f2-106">Verwenden Sie die `DeleteFile`-Methode zum Löschen der Datei.</span><span class="sxs-lookup"><span data-stu-id="2a4f2-106">Use the `DeleteFile` method to delete the file.</span></span> <span data-ttu-id="2a4f2-107">Der folgende Code veranschaulicht, wie Sie die Datei mit dem Namen `test.txt` löschen können.</span><span class="sxs-lookup"><span data-stu-id="2a4f2-107">The following code demonstrates how to delete the file named `test.txt`.</span></span>  
  
     <span data-ttu-id="2a4f2-108">[!code-vb[VbVbcnMyFileSystem#22](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2a4f2-108">[!code-vb[VbVbcnMyFileSystem#22](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_1.vb)]</span></span>  
  
### <a name="to-delete-a-text-file-and-ask-the-user-to-confirm-that-the-file-should-be-deleted"></a><span data-ttu-id="2a4f2-109">Löschen einer Textdatei und Bestätigen des Löschvorgangs der Datei durch den Benutzer</span><span class="sxs-lookup"><span data-stu-id="2a4f2-109">To delete a text file and ask the user to confirm that the file should be deleted</span></span>  
  
-   <span data-ttu-id="2a4f2-110">Verwenden Sie die `DeleteFile`-Methode zum Löschen der Datei, und legen Sie `showUI` auf `AllDialogs` fest.</span><span class="sxs-lookup"><span data-stu-id="2a4f2-110">Use the `DeleteFile` method to delete the file, setting `showUI` to `AllDialogs`.</span></span> <span data-ttu-id="2a4f2-111">Der folgende Code veranschaulicht, wie Sie die Datei mit dem Namen `test.txt` löschen können, und wie Sie dem Benutzer das Bestätigen des Löschvorgangs ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2a4f2-111">The following code demonstrates how to delete the file named `test.txt` and allow the user to confirm that the file should be deleted.</span></span>  
  
     <span data-ttu-id="2a4f2-112">[!code-vb[VbFileIOMisc#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2a4f2-112">[!code-vb[VbFileIOMisc#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_2.vb)]</span></span>  
  
### <a name="to-delete-a-text-file-and-send-it-to-the-recycle-bin"></a><span data-ttu-id="2a4f2-113">Löschen einer Textdatei und anschließendes Verschieben in den Papierkorb</span><span class="sxs-lookup"><span data-stu-id="2a4f2-113">To delete a text file and send it to the Recycle Bin</span></span>  
  
-   <span data-ttu-id="2a4f2-114">Verwenden Sie die `DeleteFile`-Methode, um die Datei zu löschen, und geben Sie `SendToRecycleBin` für den `recycle`-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="2a4f2-114">Use the `DeleteFile` method to delete the file, specifying `SendToRecycleBin` for the `recycle` parameter.</span></span> <span data-ttu-id="2a4f2-115">Der folgende Code veranschaulicht, wie Sie die Datei mit dem Namen `test.txt` löschen und sie in den **Papierkorb** verschieben können.</span><span class="sxs-lookup"><span data-stu-id="2a4f2-115">The following code demonstrates how to delete the file named `test.txt` and send it to the **Recycle Bin**.</span></span>  
  
     <span data-ttu-id="2a4f2-116">[!code-vb[VbFileIOMisc#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="2a4f2-116">[!code-vb[VbFileIOMisc#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_3.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2a4f2-117">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="2a4f2-117">Robust Programming</span></span>  
 <span data-ttu-id="2a4f2-118">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="2a4f2-118">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="2a4f2-119">Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="2a4f2-119">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="2a4f2-120">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="2a4f2-120">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="2a4f2-121">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="2a4f2-121">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="2a4f2-122">Der Pfad eines Datei- oder Ordnernamens enthält einen Doppelpunkt (:) oder weist ein ungültiges Format auf (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="2a4f2-122">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="2a4f2-123">Die Datei wird gerade verwendet (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="2a4f2-123">The file is in use (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="2a4f2-124">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="2a4f2-124">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="2a4f2-125">Die Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="2a4f2-125">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="2a4f2-126">Der Benutzer verfügt nicht über die nötigen Berechtigungen, um die Datei zu löschen, oder die Datei ist schreibgeschützt (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="2a4f2-126">The user does not have permission to delete the file, or the file is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="2a4f2-127">Ein teilweise vertrauenswürdiger Kontext, in dem der Benutzer nicht über ausreichende Berechtigungen für den Dateizugriff verfügt (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="2a4f2-127">A partial-trust situation exists in which the user does not have sufficient permissions (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="2a4f2-128">Der Benutzer hat den Vorgang abgebrochen, und `onUserCancel` wird auf `ThrowException` festgelegt (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="2a4f2-128">The user cancelled the operation and `onUserCancel` is set to `ThrowException` (<xref:System.OperationCanceledException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a4f2-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a4f2-129">See Also</span></span>  
 <span data-ttu-id="2a4f2-130"><xref:Microsoft.VisualBasic.FileIO.UICancelOption></span><span class="sxs-lookup"><span data-stu-id="2a4f2-130"><xref:Microsoft.VisualBasic.FileIO.UICancelOption></span></span>   
 <span data-ttu-id="2a4f2-131"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="2a4f2-131"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="2a4f2-132"><xref:Microsoft.VisualBasic.FileIO.UIOption></span><span class="sxs-lookup"><span data-stu-id="2a4f2-132"><xref:Microsoft.VisualBasic.FileIO.UIOption></span></span>   
 <span data-ttu-id="2a4f2-133"><xref:Microsoft.VisualBasic.FileIO.RecycleOption></span><span class="sxs-lookup"><span data-stu-id="2a4f2-133"><xref:Microsoft.VisualBasic.FileIO.RecycleOption></span></span>   
 [<span data-ttu-id="2a4f2-134">Gewusst wie: Abrufen einer Sammlung von Dateien in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="2a4f2-134">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)

