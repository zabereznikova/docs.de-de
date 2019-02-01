---
title: 'Vorgehensweise: Anfordern einer Webseite und Abrufen der Ergebnisse als Stream'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 5ef1867d84b619c58a7b3e29ed0f81f9db0c07a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54578584"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="a5c69-102">Vorgehensweise: Anfordern einer Webseite und Abrufen der Ergebnisse als Stream</span><span class="sxs-lookup"><span data-stu-id="a5c69-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="a5c69-103">In diesem Beispiel erfahren Sie, wie Sie eine Webseite anfordern und die Ergebnisse als Stream abrufen.</span><span class="sxs-lookup"><span data-stu-id="a5c69-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5c69-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5c69-104">Example</span></span>  
  
```csharp  
WebClient myClient = new WebClient();  
Stream response = myClient.OpenRead("http://www.contoso.com/index.htm");  
// The stream data is used here.  
response.Close();  
```  
  
```vb  
Dim myClient As WebClient = New WebClient()  
Dim response As Stream = myClient.OpenRead("http://www.contoso.com/index.htm")  
' The stream data is used here.  
response.Close()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a5c69-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a5c69-105">Compiling the Code</span></span>  
 <span data-ttu-id="a5c69-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a5c69-106">This example requires:</span></span>  
  
-   <span data-ttu-id="a5c69-107">Verweise auf die Namespaces <xref:System.IO> und <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="a5c69-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5c69-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5c69-108">See also</span></span>
- [<span data-ttu-id="a5c69-109">Requesting Data (Anfordern von Daten)</span><span class="sxs-lookup"><span data-stu-id="a5c69-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
