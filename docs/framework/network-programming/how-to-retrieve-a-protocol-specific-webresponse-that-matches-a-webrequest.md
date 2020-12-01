---
title: 'Vorgehensweise: Abrufen einer protokollspezifischen WebResponse-Klasse, die einer WebRequest-Klasse entspricht'
description: Hier erfahren Sie, wie Sie eine protokollspezifische WebResponse-Klasse abrufen, die einer WebRequest-Klasse im .NET Framework entspricht.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: fd163c115dcd19c05f93f4c202b043440834ba9d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266739"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="32b5f-103">Vorgehensweise: Abrufen einer protokollspezifischen WebResponse-Klasse, die einer WebRequest-Klasse entspricht</span><span class="sxs-lookup"><span data-stu-id="32b5f-103">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>

<span data-ttu-id="32b5f-104">In diesem Beispiel erfahren Sie, wie Sie ein protokollspezifisches WebResponse abrufen, das einem WebRequest entspricht.</span><span class="sxs-lookup"><span data-stu-id="32b5f-104">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32b5f-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="32b5f-105">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="32b5f-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="32b5f-106">Compiling the Code</span></span>  

 <span data-ttu-id="32b5f-107">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="32b5f-107">This example requires:</span></span>  
  
- <span data-ttu-id="32b5f-108">Verweise auf den Namespace **System.Net**</span><span class="sxs-lookup"><span data-stu-id="32b5f-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32b5f-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32b5f-109">See also</span></span>

- [<span data-ttu-id="32b5f-110">Requesting Data (Anfordern von Daten)</span><span class="sxs-lookup"><span data-stu-id="32b5f-110">Requesting Data</span></span>](requesting-data.md)
