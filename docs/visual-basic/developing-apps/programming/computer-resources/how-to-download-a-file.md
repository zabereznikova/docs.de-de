---
title: 'Gewusst wie: Downloaden einer Datei in Visual Basic'
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
- downloading Internet resources, files
- downloading files
- remote computers, downloading from
- files, downloading
- files, transferring
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
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
ms.openlocfilehash: 8988b922df921c2de3e2c4f6d7a8e98887ba7b0a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-download-a-file-in-visual-basic"></a><span data-ttu-id="e8c23-102">Gewusst wie: Downloaden einer Datei in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e8c23-102">How to: Download a File in Visual Basic</span></span>
<span data-ttu-id="e8c23-103">Die <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>-Methode kann zum Herunterladen einer Remotedatei und dazu verwendet werden, diese an einem bestimmten Speicherort zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e8c23-103">The <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> method can be used to download a remote file and store it to a specific location.</span></span> <span data-ttu-id="e8c23-104">Wenn der `ShowUI`-Parameter auf `True` festgelegt wird, wir ein Dialogfeld angezeigt, das den Fortschritt des Downloads anzeigt und Benutzern erlaubt, den Vorgang abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="e8c23-104">If the `ShowUI` parameter is set to `True`, a dialog box is displayed showing the progress of the download and allowing users to cancel the operation.</span></span> <span data-ttu-id="e8c23-105">Standardmäßig werden vorhandene Dateien mit demselben Namen nicht überschrieben. Wenn vorhandene Dateien überschrieben werden sollen, legen Sie den `overwrite`-Parameter auf `True` fest.</span><span class="sxs-lookup"><span data-stu-id="e8c23-105">By default, existing files having the same name are not overwritten; if you want to overwrite existing files, set the `overwrite` parameter to `True`.</span></span>  
  
 <span data-ttu-id="e8c23-106">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="e8c23-106">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="e8c23-107">Der Laufwerksname ist ungültig (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="e8c23-107">Drive name is not valid (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="e8c23-108">Die erforderliche Authentifizierung wurde nicht bereitgestellt (<xref:System.UnauthorizedAccessException> oder <xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="e8c23-108">Necessary authentication has not been supplied (<xref:System.UnauthorizedAccessException> or <xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="e8c23-109">Der Server antwortet nicht innerhalb der angegebenen `connectionTimeout` (<xref:System.TimeoutException>).</span><span class="sxs-lookup"><span data-stu-id="e8c23-109">The server does not respond within the specified `connectionTimeout` (<xref:System.TimeoutException>).</span></span>  
  
-   <span data-ttu-id="e8c23-110">Die Anforderung wird von der Website verweigert (<xref:System.Net.WebException>).</span><span class="sxs-lookup"><span data-stu-id="e8c23-110">The request is denied by the Web site (<xref:System.Net.WebException>).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
> [!IMPORTANT]
>  <span data-ttu-id="e8c23-111">Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.</span><span class="sxs-lookup"><span data-stu-id="e8c23-111">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="e8c23-112">Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="e8c23-112">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="e8c23-113">Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8c23-113">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="e8c23-114">Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="e8c23-114">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
### <a name="to-download-a-file"></a><span data-ttu-id="e8c23-115">So laden Sie eine Datei herunter</span><span class="sxs-lookup"><span data-stu-id="e8c23-115">To download a file</span></span>  
  
-   <span data-ttu-id="e8c23-116">Verwenden Sie die `DownloadFile`-Methode zum Herunterladen der Datei. Geben Sie dabei den Speicherort der Zieldatei als Zeichenfolge oder URI an, und geben Sie den Speicherort an, an dem die Datei gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8c23-116">Use the `DownloadFile` method to download the file, specifying the target file's location as a string or URI and specifying the location at which to store the file.</span></span> <span data-ttu-id="e8c23-117">Dieses Beispiel lädt die `WineList.txt`-Datei von `http://www.cohowinery.com/downloads` herunter und speichert sie unter `C:\Documents and Settings\All Users\Documents`:</span><span class="sxs-lookup"><span data-stu-id="e8c23-117">This example downloads the file `WineList.txt` from `http://www.cohowinery.com/downloads` and saves it to `C:\Documents and Settings\All Users\Documents`:</span></span>  
  
     <span data-ttu-id="e8c23-118">[!code-vb[VbResourceTasks#9](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e8c23-118">[!code-vb[VbResourceTasks#9](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_1.vb)]</span></span>  
  
### <a name="to-download-a-file-specifying-a-time-out-interval"></a><span data-ttu-id="e8c23-119">So laden Sie eine Datei herunter und geben ein Timeoutintervall an</span><span class="sxs-lookup"><span data-stu-id="e8c23-119">To download a file, specifying a time-out interval</span></span>  
  
-   <span data-ttu-id="e8c23-120">Verwenden Sie die `DownloadFile`-Methode, um die Datei herunterzuladen. Geben Sie dabei den Speicherort der Zieldatei als Zeichenfolge oder URI an sowie den Speicherort, an dem die Datei gespeichert werden soll. Geben Sie ebenso das Timeoutintervall in Millisekunden an (der Standardwert ist 1000).</span><span class="sxs-lookup"><span data-stu-id="e8c23-120">Use the `DownloadFile` method to download the file, specifying the target file's location as a string or URI, specifying the location at which to store the file, and specifying the time-out interval in milliseconds (the default is 1000).</span></span> <span data-ttu-id="e8c23-121">In diesem Beispiel wird die `WineList.txt`-Datei von `http://www.cohowinery.com/downloads` heruntergeladen und unter `C:\Documents and Settings\All Users\Documents` gespeichert, wobei ein Timeoutintervall von 500 Millisekunden angegeben ist:</span><span class="sxs-lookup"><span data-stu-id="e8c23-121">This example downloads the file `WineList.txt` from `http://www.cohowinery.com/downloads` and saves it to `C:\Documents and Settings\All Users\Documents`, specifying a time-out interval of 500 milliseconds:</span></span>  
  
     <span data-ttu-id="e8c23-122">[!code-vb[VbResourceTasks#10](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e8c23-122">[!code-vb[VbResourceTasks#10](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_2.vb)]</span></span>  
  
### <a name="to-download-a-file-supplying-a-user-name-and-password"></a><span data-ttu-id="e8c23-123">So laden Sie eine Datei unter Angabe eines Benutzernamens und Kennworts herunter</span><span class="sxs-lookup"><span data-stu-id="e8c23-123">To download a file, supplying a user name and password</span></span>  
  
-   <span data-ttu-id="e8c23-124">Verwenden Sie die `DownLoadFile`-Methode zum Herunterladen der Datei. Geben Sie dabei den Speicherort der Zieldatei als Zeichenfolge oder URI an, und geben Sie den Speicherort an, an dem die Datei gespeichert werden soll, sowie den Benutzernamen und das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="e8c23-124">Use the `DownLoadFile` method to download the file, specifying the target file's location as a string or URI and specifying the location at which to store the file, the user name, and the password.</span></span> <span data-ttu-id="e8c23-125">In diesem Beispiel wird die `WineList.txt`-Datei von `http://www.cohowinery.com/downloads` heruntergeladen und unter `C:\Documents and Settings\All Users\Documents` mit dem Benutzernamen `anonymous` und einem leeren Kennwort gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e8c23-125">This example downloads the file `WineList.txt` from `http://www.cohowinery.com/downloads` and saves it to `C:\Documents and Settings\All Users\Documents`, with the user name `anonymous` and a blank password.</span></span>  
  
     <span data-ttu-id="e8c23-126">[!code-vb[VbResourceTasks#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="e8c23-126">[!code-vb[VbResourceTasks#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_3.vb)]</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e8c23-127">Das FTP-Protokoll, das von der `DownLoadFile`-Methode verwendet wird, sendet Informationen in Klartext, einschließlich Kennwörter, und darf nicht für die Übermittlung vertraulicher Informationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e8c23-127">The FTP protocol used by the `DownLoadFile` method sends information, including passwords, in plain text and should not be used for transmitting sensitive information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8c23-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8c23-128">See Also</span></span>  
 <span data-ttu-id="e8c23-129"><xref:Microsoft.VisualBasic.Devices.Network></span><span class="sxs-lookup"><span data-stu-id="e8c23-129"><xref:Microsoft.VisualBasic.Devices.Network></span></span>   
 <span data-ttu-id="e8c23-130"><xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A></span><span class="sxs-lookup"><span data-stu-id="e8c23-130"><xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A></span></span>   
 <span data-ttu-id="e8c23-131">[Gewusst wie: Hochladen einer Datei](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md) </span><span class="sxs-lookup"><span data-stu-id="e8c23-131">[How to: Upload a File](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md) </span></span>  
 [<span data-ttu-id="e8c23-132">Gewusst wie: Analysieren von Dateipfaden</span><span class="sxs-lookup"><span data-stu-id="e8c23-132">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)

