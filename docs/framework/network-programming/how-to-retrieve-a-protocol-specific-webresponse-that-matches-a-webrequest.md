---
title: 'Gewusst wie: Abrufen eines protokollspezifischen WebResponse, das einem WebRequest entspricht'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: 0cb2d11306f52df767d8c053e8ab745696bb8e47
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048138"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="0516e-102">Gewusst wie: Abrufen eines protokollspezifischen WebResponse, das einem WebRequest entspricht</span><span class="sxs-lookup"><span data-stu-id="0516e-102">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="0516e-103">In diesem Beispiel erfahren Sie, wie Sie ein protokollspezifisches WebResponse abrufen, das einem WebRequest entspricht.</span><span class="sxs-lookup"><span data-stu-id="0516e-103">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0516e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0516e-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0516e-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0516e-105">Compiling the Code</span></span>  
 <span data-ttu-id="0516e-106">Dieses Beispiel erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0516e-106">This example requires:</span></span>  
  
- <span data-ttu-id="0516e-107">Verweise auf den Namespace **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="0516e-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0516e-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0516e-108">See also</span></span>

- [<span data-ttu-id="0516e-109">Anfordern von Daten</span><span class="sxs-lookup"><span data-stu-id="0516e-109">Requesting Data</span></span>](requesting-data.md)
