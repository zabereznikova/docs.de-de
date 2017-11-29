---
title: 'Gewusst wie: Abrufen eines protokollspezifischen WebResponse, das einem WebRequest entspricht'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: cbf6b6eab3502f8f04f33f6f11d5d071e3406a7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="6b7a1-102">Gewusst wie: Abrufen eines protokollspezifischen WebResponse, das einem WebRequest entspricht</span><span class="sxs-lookup"><span data-stu-id="6b7a1-102">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="6b7a1-103">In diesem Beispiel erfahren Sie, wie Sie ein protokollspezifisches WebResponse abrufen, das einem WebRequest entspricht.</span><span class="sxs-lookup"><span data-stu-id="6b7a1-103">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b7a1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b7a1-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6b7a1-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6b7a1-105">Compiling the Code</span></span>  
 <span data-ttu-id="6b7a1-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6b7a1-106">This example requires:</span></span>  
  
-   <span data-ttu-id="6b7a1-107">Verweise auf den Namespace **System.Net**</span><span class="sxs-lookup"><span data-stu-id="6b7a1-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b7a1-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b7a1-108">See Also</span></span>  
 [<span data-ttu-id="6b7a1-109">Anfordern von Daten</span><span class="sxs-lookup"><span data-stu-id="6b7a1-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
