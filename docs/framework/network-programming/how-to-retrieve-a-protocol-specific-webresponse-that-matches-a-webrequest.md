---
title: 'Vorgehensweise: Abrufen einer protokollspezifischen WebResponse-Klasse, die einer WebRequest-Klasse entspricht'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: 3b3b523d6248b3c61a0994728b035bc6f02d5cf1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745347"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="9a244-102">Vorgehensweise: Abrufen einer protokollspezifischen WebResponse-Klasse, die einer WebRequest-Klasse entspricht</span><span class="sxs-lookup"><span data-stu-id="9a244-102">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="9a244-103">In diesem Beispiel erfahren Sie, wie Sie ein protokollspezifisches WebResponse abrufen, das einem WebRequest entspricht.</span><span class="sxs-lookup"><span data-stu-id="9a244-103">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a244-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9a244-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9a244-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9a244-105">Compiling the Code</span></span>  
 <span data-ttu-id="9a244-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9a244-106">This example requires:</span></span>  
  
-   <span data-ttu-id="9a244-107">Verweise auf den Namespace **System.Net**</span><span class="sxs-lookup"><span data-stu-id="9a244-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a244-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a244-108">See also</span></span>
- [<span data-ttu-id="9a244-109">Requesting Data (Anfordern von Daten)</span><span class="sxs-lookup"><span data-stu-id="9a244-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
