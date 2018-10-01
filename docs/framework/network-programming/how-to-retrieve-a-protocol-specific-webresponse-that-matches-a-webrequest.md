---
title: 'Gewusst wie: Abrufen eines protokollspezifischen WebResponse, das einem WebRequest entspricht'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2a72e57156903c9d436a49aaf6da596868af4003
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47454868"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="ccc0d-102">Gewusst wie: Abrufen eines protokollspezifischen WebResponse, das einem WebRequest entspricht</span><span class="sxs-lookup"><span data-stu-id="ccc0d-102">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="ccc0d-103">In diesem Beispiel erfahren Sie, wie Sie ein protokollspezifisches WebResponse abrufen, das einem WebRequest entspricht.</span><span class="sxs-lookup"><span data-stu-id="ccc0d-103">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccc0d-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ccc0d-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ccc0d-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ccc0d-105">Compiling the Code</span></span>  
 <span data-ttu-id="ccc0d-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ccc0d-106">This example requires:</span></span>  
  
-   <span data-ttu-id="ccc0d-107">Verweise auf den Namespace **System.Net**</span><span class="sxs-lookup"><span data-stu-id="ccc0d-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc0d-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccc0d-108">See Also</span></span>  
 [<span data-ttu-id="ccc0d-109">Requesting Data (Anfordern von Daten)</span><span class="sxs-lookup"><span data-stu-id="ccc0d-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
