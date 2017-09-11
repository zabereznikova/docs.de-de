---
title: 'Gewusst wie: Hochladen einer Datei in Visual Basic'
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
- networks, uploading files
- files, uploading
- uploading files
- UploadFile method
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
caps.latest.revision: 22
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
ms.openlocfilehash: 29baf1f420cece6e0b05f9638b30a326178a013d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-upload-a-file-in-visual-basic"></a><span data-ttu-id="93da2-102">Gewusst wie: Hochladen einer Datei in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93da2-102">How to: Upload a File in Visual Basic</span></span>
<span data-ttu-id="93da2-103">Die <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>-Methode kann zum Hochladen einer Datei und zum Speichern derselben an einem Remotespeicherort verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="93da2-103">The <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> method can be used to upload a file and store it to a remote location.</span></span> <span data-ttu-id="93da2-104">Wenn der `ShowUI`-Parameter auf `True` festgelegt wird, wir ein Dialogfeld angezeigt, das den Fortschritt des Hochladens anzeigt und Benutzern erlaubt, den Vorgang abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="93da2-104">If the `ShowUI` parameter is set to `True`, a dialog box is displayed that shows the progress of the upload and allows users to cancel the operation.</span></span>  
  
### <a name="to-upload-a-file"></a><span data-ttu-id="93da2-105">Hochladen einer Datei</span><span class="sxs-lookup"><span data-stu-id="93da2-105">To upload a file</span></span>  
  
-   <span data-ttu-id="93da2-106">Verwenden Sie die `UploadFile`-Methode, um eine Datei hochzuladen, und geben Sie den Speicherort der Quelldatei und des Zielverzeichnisses als Zeichenfolge oder URI (Uniform Resource Identifier) an. In diesem Beispiel wird die Datei `Order.txt` in `http://www.cohowinery.com/uploads.aspx` hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="93da2-106">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI (Uniform Resource Identifier).This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`.</span></span>  
  
     <span data-ttu-id="93da2-107">[!code-vb[VbResourceTasks#6](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="93da2-107">[!code-vb[VbResourceTasks#6](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_1.vb)]</span></span>  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a><span data-ttu-id="93da2-108">Hochladen einer Datei und Anzeigen des Fortschritts des Vorgangs</span><span class="sxs-lookup"><span data-stu-id="93da2-108">To upload a file and show the progress of the operation</span></span>  
  
-   <span data-ttu-id="93da2-109">Verwenden Sie die `UploadFile`-Methode, um eine Datei hochzuladen, und geben Sie den Speicherort der Quelldatei und des Zielverzeichnisses als Zeichenfolge oder URI an.</span><span class="sxs-lookup"><span data-stu-id="93da2-109">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI.</span></span> <span data-ttu-id="93da2-110">In diesem Beispiel wird `Order.txt` ohne Benutzername und Kennwort in `http://www.cohowinery.com/uploads.aspx` hochgeladen. Der Hochladeprozess wird gezeigt. Das Timeoutintervall beträgt 500 Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="93da2-110">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx` without supplying a user name or password, shows the progress of the upload, and has a time-out interval of 500 milliseconds.</span></span>  
  
     <span data-ttu-id="93da2-111">[!code-vb[VbResourceTasks#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="93da2-111">[!code-vb[VbResourceTasks#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_2.vb)]</span></span>  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a><span data-ttu-id="93da2-112">So laden Sie eine Datei unter Angabe eines Benutzernamens und Kennworts hoch</span><span class="sxs-lookup"><span data-stu-id="93da2-112">To upload a file, supplying a user name and password</span></span>  
  
-   <span data-ttu-id="93da2-113">Verwenden Sie die `UploadFile`-Methode zum Hochladen der Datei. Geben Sie dabei den Speicherort der Quelldatei und des Zielverzeichnisses als Zeichenfolge oder URI an, und geben Sie den Benutzernamen und das Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="93da2-113">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI, and specifying the user name and the password.</span></span> <span data-ttu-id="93da2-114">In diesem Beispiel wird die Datei `Order.txt` in `http://www.cohowinery.com/uploads.aspx` hochgeladen. Der Benutzername `anonymous` und ein leeres Kennwort werden bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="93da2-114">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`, supplying the user name `anonymous` and a blank password.</span></span>  
  
     <span data-ttu-id="93da2-115">[!code-vb[VbResourceTasks#8](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="93da2-115">[!code-vb[VbResourceTasks#8](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_3.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="93da2-116">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="93da2-116">Robust Programming</span></span>  
 <span data-ttu-id="93da2-117">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="93da2-117">The following conditions may throw an exception:</span></span>  
  
-   <span data-ttu-id="93da2-118">Der Dateipfad ist ungültig (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="93da2-118">The local file path is not valid (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="93da2-119">Die Authentifizierung ist fehlgeschlagen (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="93da2-119">Authentication failed (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="93da2-120">Verbindungstimeout (<xref:System.TimeoutException>)</span><span class="sxs-lookup"><span data-stu-id="93da2-120">The connection timed out (<xref:System.TimeoutException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93da2-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93da2-121">See Also</span></span>  
 <span data-ttu-id="93da2-122"><xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="93da2-122"><xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName></span></span>   
 <span data-ttu-id="93da2-123"><xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A></span><span class="sxs-lookup"><span data-stu-id="93da2-123"><xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A></span></span>   
 <span data-ttu-id="93da2-124">[Vorgehensweise: Herunterladen einer Datei](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md) </span><span class="sxs-lookup"><span data-stu-id="93da2-124">[How to: Download a File](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md) </span></span>  
 [<span data-ttu-id="93da2-125">Gewusst wie: Analysieren von Dateipfaden</span><span class="sxs-lookup"><span data-stu-id="93da2-125">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)

