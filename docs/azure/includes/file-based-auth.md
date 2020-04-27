---
ms.service: multiple
ms.date: 9/20/2018
ms.topic: include
ms.openlocfilehash: bfa7bcefff45bc325d7bba3aa2b9b3a8f0d439fa
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433157"
---
<span data-ttu-id="669df-101">Erstellen Sie eine Textdatei namens `azureauth.json`.</span><span class="sxs-lookup"><span data-stu-id="669df-101">Create a text file named `azureauth.json`.</span></span> <span data-ttu-id="669df-102">Fügen Sie die JSON-Ausgabe ein, die Sie beim Erstellen des Dienstprinzipals erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="669df-102">Paste the JSON output from when you created the service principal.</span></span>

<span data-ttu-id="669df-103">Speichern Sie diese Datei an einem sicheren Ort in Ihrem System, an dem sie vom Code gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="669df-103">Save this file in a secure location on your system where your code can read it.</span></span> <span data-ttu-id="669df-104">Verwenden Sie PowerShell zum Festlegen einer Umgebungsvariablen mit dem Namen `AZURE_AUTH_LOCATION` mit dem vollständigen Pfad zur Datei, z.B.:</span><span class="sxs-lookup"><span data-stu-id="669df-104">Use PowerShell to set an environment variable named `AZURE_AUTH_LOCATION` with the full path to the file, for example:</span></span>

```powershell
[Environment]::SetEnvironmentVariable("AZURE_AUTH_LOCATION", "C:\src\azureauth.json", "User")
```
