---
title: 'Vorgehensweise: Typumwandlung einer WebRequest-Klasse in protokollspezifische Zugriffseigenschaften'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
ms.openlocfilehash: a9488e484aad7ba3df23c33b2cb5b79f234b758e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088365"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a><span data-ttu-id="1ba2e-102">Vorgehensweise: Typumwandlung einer WebRequest-Klasse in protokollspezifische Zugriffseigenschaften</span><span class="sxs-lookup"><span data-stu-id="1ba2e-102">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>
<span data-ttu-id="1ba2e-103">Dieses Beispiel zeigt, wie die Typumwandlung für ein WebRequest durchgeführt wird, sodass Sie auf protokollspezifische Eigenschaften zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1ba2e-103">This example shows how to typecast a WebRequest so that you can access protocol specific properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ba2e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ba2e-104">Example</span></span>  
  
```csharp  
HttpWebRequest httpreq =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ba2e-105">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ba2e-105">See also</span></span>

- [<span data-ttu-id="1ba2e-106">Programmieren austauschbarer Protokolle</span><span class="sxs-lookup"><span data-stu-id="1ba2e-106">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
