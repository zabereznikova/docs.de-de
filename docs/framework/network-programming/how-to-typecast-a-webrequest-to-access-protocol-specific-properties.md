---
title: 'Gewusst wie: Typumwandlung für ein WebRequest in zugriffsprotokollspezifische Eigenschaften'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
ms.openlocfilehash: d38a40aa1e6e3db769aedfc440077721cdfaf06d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180753"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a><span data-ttu-id="d397b-102">Gewusst wie: Typumwandlung für ein WebRequest in zugriffsprotokollspezifische Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d397b-102">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>
<span data-ttu-id="d397b-103">Dieses Beispiel zeigt, wie die Typumwandlung für ein WebRequest durchgeführt wird, sodass Sie auf protokollspezifische Eigenschaften zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="d397b-103">This example shows how to typecast a WebRequest so that you can access protocol specific properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d397b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d397b-104">Example</span></span>  
  
```csharp  
HttpWebRequest httpreq =
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a><span data-ttu-id="d397b-105">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d397b-105">See also</span></span>

- [<span data-ttu-id="d397b-106">Programming Pluggable Protocols (Programmieren austauschbarer Protokolle)</span><span class="sxs-lookup"><span data-stu-id="d397b-106">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)
