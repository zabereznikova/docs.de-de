---
title: 'Gewusst wie: Typumwandlung für ein WebRequest in zugriffsprotokollspezifische Eigenschaften'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
author: mcleblanc
ms.author: markl
ms.openlocfilehash: b4cde78ead9bdb8becf0f12497f4b37ad5a73bb3
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "47421526"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a><span data-ttu-id="b4826-102">Gewusst wie: Typumwandlung für ein WebRequest in zugriffsprotokollspezifische Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b4826-102">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>
<span data-ttu-id="b4826-103">Dieses Beispiel zeigt, wie die Typumwandlung für ein WebRequest durchgeführt wird, sodass Sie auf protokollspezifische Eigenschaften zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="b4826-103">This example shows how to typecast a WebRequest so that you can access protocol specific properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4826-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4826-104">Example</span></span>  
  
```csharp  
HttpWebRequest httpreq =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4826-105">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4826-105">See Also</span></span>  
 [<span data-ttu-id="b4826-106">Programmieren austauschbarer Protokolle</span><span class="sxs-lookup"><span data-stu-id="b4826-106">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
