---
title: 'Gewusst wie: Downloaden einer Datei'
ms.date: 07/20/2015
helpviewer_keywords:
- downloading Internet resources [Visual Basic], files
- downloading files [Visual Basic]
- remote computers [Visual Basic], downloading from
- files [Visual Basic], downloading
- files [Visual Basic], transferring
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
ms.openlocfilehash: 4923feb46ff638de9514a4d70fc00367491a6f44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345620"
---
# <a name="how-to-download-a-file-in-visual-basic"></a><span data-ttu-id="bb386-102">Gewusst wie: Downloaden einer Datei in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bb386-102">How to: Download a File in Visual Basic</span></span>

<span data-ttu-id="bb386-103">Die <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>-Methode kann zum Herunterladen einer Remotedatei und dazu verwendet werden, diese an einem bestimmten Speicherort zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bb386-103">The <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> method can be used to download a remote file and store it to a specific location.</span></span> <span data-ttu-id="bb386-104">Wenn der `ShowUI`-Parameter auf `True` festgelegt wird, wir ein Dialogfeld angezeigt, das den Fortschritt des Downloads anzeigt und Benutzern erlaubt, den Vorgang abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="bb386-104">If the `ShowUI` parameter is set to `True`, a dialog box is displayed showing the progress of the download and allowing users to cancel the operation.</span></span> <span data-ttu-id="bb386-105">Standardmäßig werden vorhandene Dateien mit demselben Namen nicht überschrieben. Wenn vorhandene Dateien überschrieben werden sollen, legen Sie den `overwrite`-Parameter auf `True` fest.</span><span class="sxs-lookup"><span data-stu-id="bb386-105">By default, existing files having the same name are not overwritten; if you want to overwrite existing files, set the `overwrite` parameter to `True`.</span></span>

<span data-ttu-id="bb386-106">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="bb386-106">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="bb386-107">Der Laufwerksname ist ungültig (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="bb386-107">Drive name is not valid (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="bb386-108">Die erforderliche Authentifizierung wurde nicht bereitgestellt (<xref:System.UnauthorizedAccessException> oder <xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="bb386-108">Necessary authentication has not been supplied (<xref:System.UnauthorizedAccessException> or <xref:System.Security.SecurityException>).</span></span>

- <span data-ttu-id="bb386-109">Der Server antwortet nicht innerhalb der angegebenen `connectionTimeout` (<xref:System.TimeoutException>).</span><span class="sxs-lookup"><span data-stu-id="bb386-109">The server does not respond within the specified `connectionTimeout` (<xref:System.TimeoutException>).</span></span>

- <span data-ttu-id="bb386-110">Die Anforderung wird von der Website verweigert (<xref:System.Net.WebException>).</span><span class="sxs-lookup"><span data-stu-id="bb386-110">The request is denied by the Web site (<xref:System.Net.WebException>).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

> [!IMPORTANT]
> <span data-ttu-id="bb386-111">Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.</span><span class="sxs-lookup"><span data-stu-id="bb386-111">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="bb386-112">Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="bb386-112">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="bb386-113">Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb386-113">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="bb386-114">Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="bb386-114">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>

### <a name="to-download-a-file"></a><span data-ttu-id="bb386-115">So laden Sie eine Datei herunter</span><span class="sxs-lookup"><span data-stu-id="bb386-115">To download a file</span></span>

- <span data-ttu-id="bb386-116">Verwenden Sie die `DownloadFile`-Methode zum Herunterladen der Datei. Geben Sie dabei den Speicherort der Zieldatei als Zeichenfolge oder URI an, und geben Sie den Speicherort an, an dem die Datei gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bb386-116">Use the `DownloadFile` method to download the file, specifying the target file's location as a string or URI and specifying the location at which to store the file.</span></span> <span data-ttu-id="bb386-117">Dieses Beispiel lädt die `WineList.txt`-Datei von `http://www.cohowinery.com/downloads` herunter und speichert sie unter `C:\Documents and Settings\All Users\Documents`:</span><span class="sxs-lookup"><span data-stu-id="bb386-117">This example downloads the file `WineList.txt` from `http://www.cohowinery.com/downloads` and saves it to `C:\Documents and Settings\All Users\Documents`:</span></span>

  [!code-vb[VbResourceTasks#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#9)]

### <a name="to-download-a-file-specifying-a-time-out-interval"></a><span data-ttu-id="bb386-118">So laden Sie eine Datei herunter und geben ein Timeoutintervall an</span><span class="sxs-lookup"><span data-stu-id="bb386-118">To download a file, specifying a time-out interval</span></span>

- <span data-ttu-id="bb386-119">Verwenden Sie die `DownloadFile`-Methode, um die Datei herunterzuladen. Geben Sie dabei den Speicherort der Zieldatei als Zeichenfolge oder URI an sowie den Speicherort, an dem die Datei gespeichert werden soll. Geben Sie ebenso das Timeoutintervall in Millisekunden an (der Standardwert ist 1000).</span><span class="sxs-lookup"><span data-stu-id="bb386-119">Use the `DownloadFile` method to download the file, specifying the target file's location as a string or URI, specifying the location at which to store the file, and specifying the time-out interval in milliseconds (the default is 1000).</span></span> <span data-ttu-id="bb386-120">In diesem Beispiel wird die `WineList.txt`-Datei von `http://www.cohowinery.com/downloads` heruntergeladen und unter `C:\Documents and Settings\All Users\Documents` gespeichert, wobei ein Timeoutintervall von 500 Millisekunden angegeben ist:</span><span class="sxs-lookup"><span data-stu-id="bb386-120">This example downloads the file `WineList.txt` from `http://www.cohowinery.com/downloads` and saves it to `C:\Documents and Settings\All Users\Documents`, specifying a time-out interval of 500 milliseconds:</span></span>

  [!code-vb[VbResourceTasks#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#10)]

### <a name="to-download-a-file-supplying-a-user-name-and-password"></a><span data-ttu-id="bb386-121">So laden Sie eine Datei unter Angabe eines Benutzernamens und Kennworts herunter</span><span class="sxs-lookup"><span data-stu-id="bb386-121">To download a file, supplying a user name and password</span></span>

- <span data-ttu-id="bb386-122">Verwenden Sie die `DownLoadFile`-Methode zum Herunterladen der Datei. Geben Sie dabei den Speicherort der Zieldatei als Zeichenfolge oder URI an, und geben Sie den Speicherort an, an dem die Datei gespeichert werden soll, sowie den Benutzernamen und das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="bb386-122">Use the `DownLoadFile` method to download the file, specifying the target file's location as a string or URI and specifying the location at which to store the file, the user name, and the password.</span></span> <span data-ttu-id="bb386-123">In diesem Beispiel wird die `WineList.txt`-Datei von `http://www.cohowinery.com/downloads` heruntergeladen und unter `C:\Documents and Settings\All Users\Documents` mit dem Benutzernamen `anonymous` und einem leeren Kennwort gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bb386-123">This example downloads the file `WineList.txt` from `http://www.cohowinery.com/downloads` and saves it to `C:\Documents and Settings\All Users\Documents`, with the user name `anonymous` and a blank password.</span></span>

  [!code-vb[VbResourceTasks#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#11)]

  > [!IMPORTANT]
  > <span data-ttu-id="bb386-124">Das FTP-Protokoll, das von der `DownLoadFile`-Methode verwendet wird, sendet Informationen in Klartext, einschließlich Kennwörter, und darf nicht für die Übermittlung vertraulicher Informationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb386-124">The FTP protocol used by the `DownLoadFile` method sends information, including passwords, in plain text and should not be used for transmitting sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb386-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb386-125">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Network>
- <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>
- [<span data-ttu-id="bb386-126">Gewusst wie: Hochladen einer Datei</span><span class="sxs-lookup"><span data-stu-id="bb386-126">How to: Upload a File</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)
- [<span data-ttu-id="bb386-127">Gewusst wie: Analysieren von Dateipfaden</span><span class="sxs-lookup"><span data-stu-id="bb386-127">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
