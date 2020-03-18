---
title: 'Gewusst wie: Hochladen einer Datei'
ms.date: 07/20/2015
helpviewer_keywords:
- networks, uploading files
- files [Visual Basic], uploading
- uploading files [Visual Basic]
- UploadFile method [Visual Basic]
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
ms.openlocfilehash: 52b731606c74ab7ff06a42dfdbe078616ba33d88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345562"
---
# <a name="how-to-upload-a-file-in-visual-basic"></a><span data-ttu-id="a7b29-102">Gewusst wie: Hochladen einer Datei in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a7b29-102">How to: Upload a File in Visual Basic</span></span>

<span data-ttu-id="a7b29-103">Die <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>-Methode kann zum Hochladen einer Datei und zum Speichern derselben an einem Remotespeicherort verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a7b29-103">The <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> method can be used to upload a file and store it to a remote location.</span></span> <span data-ttu-id="a7b29-104">Wenn der `ShowUI`-Parameter auf `True` festgelegt wird, wir ein Dialogfeld angezeigt, das den Fortschritt des Hochladens anzeigt und Benutzern erlaubt, den Vorgang abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="a7b29-104">If the `ShowUI` parameter is set to `True`, a dialog box is displayed that shows the progress of the upload and allows users to cancel the operation.</span></span>  
  
### <a name="to-upload-a-file"></a><span data-ttu-id="a7b29-105">Hochladen einer Datei</span><span class="sxs-lookup"><span data-stu-id="a7b29-105">To upload a file</span></span>  
  
- <span data-ttu-id="a7b29-106">Verwenden Sie die `UploadFile`-Methode, um eine Datei hochzuladen, und geben Sie den Speicherort der Quelldatei und des Zielverzeichnisses als Zeichenfolge oder URI (Uniform Resource Identifier) an. In diesem Beispiel wird die Datei `Order.txt` in `http://www.cohowinery.com/uploads.aspx` hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="a7b29-106">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI (Uniform Resource Identifier).This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`.</span></span>  
  
     [!code-vb[VbResourceTasks#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#6)]  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a><span data-ttu-id="a7b29-107">Hochladen einer Datei und Anzeigen des Fortschritts des Vorgangs</span><span class="sxs-lookup"><span data-stu-id="a7b29-107">To upload a file and show the progress of the operation</span></span>  
  
- <span data-ttu-id="a7b29-108">Verwenden Sie die `UploadFile`-Methode, um eine Datei hochzuladen, und geben Sie den Speicherort der Quelldatei und des Zielverzeichnisses als Zeichenfolge oder URI an.</span><span class="sxs-lookup"><span data-stu-id="a7b29-108">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI.</span></span> <span data-ttu-id="a7b29-109">In diesem Beispiel wird `Order.txt` ohne Benutzername und Kennwort in `http://www.cohowinery.com/uploads.aspx` hochgeladen. Der Hochladeprozess wird gezeigt. Das Timeoutintervall beträgt 500 Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="a7b29-109">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx` without supplying a user name or password, shows the progress of the upload, and has a time-out interval of 500 milliseconds.</span></span>  
  
     [!code-vb[VbResourceTasks#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#7)]  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a><span data-ttu-id="a7b29-110">So laden Sie eine Datei unter Angabe eines Benutzernamens und Kennworts hoch</span><span class="sxs-lookup"><span data-stu-id="a7b29-110">To upload a file, supplying a user name and password</span></span>  
  
- <span data-ttu-id="a7b29-111">Verwenden Sie die `UploadFile`-Methode zum Hochladen der Datei. Geben Sie dabei den Speicherort der Quelldatei und des Zielverzeichnisses als Zeichenfolge oder URI an, und geben Sie den Benutzernamen und das Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="a7b29-111">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI, and specifying the user name and the password.</span></span> <span data-ttu-id="a7b29-112">In diesem Beispiel wird die Datei `Order.txt` in `http://www.cohowinery.com/uploads.aspx` hochgeladen. Der Benutzername `anonymous` und ein leeres Kennwort werden bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a7b29-112">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`, supplying the user name `anonymous` and a blank password.</span></span>  
  
     [!code-vb[VbResourceTasks#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a7b29-113">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="a7b29-113">Robust Programming</span></span>  

 <span data-ttu-id="a7b29-114">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="a7b29-114">The following conditions may throw an exception:</span></span>  
  
- <span data-ttu-id="a7b29-115">Der Dateipfad ist ungültig (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="a7b29-115">The local file path is not valid (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="a7b29-116">Die Authentifizierung ist fehlgeschlagen (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="a7b29-116">Authentication failed (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="a7b29-117">Verbindungstimeout (<xref:System.TimeoutException>)</span><span class="sxs-lookup"><span data-stu-id="a7b29-117">The connection timed out (<xref:System.TimeoutException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7b29-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7b29-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>
- [<span data-ttu-id="a7b29-119">Gewusst wie: Herunterladen einer Datei</span><span class="sxs-lookup"><span data-stu-id="a7b29-119">How to: Download a File</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md)
- [<span data-ttu-id="a7b29-120">Gewusst wie: Analysieren von Dateipfaden</span><span class="sxs-lookup"><span data-stu-id="a7b29-120">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
