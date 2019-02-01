---
title: 'Vorgehensweise: Überschreiben einer globalen Proxyauswahl'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 6973503f12e0e60ee139c5cd7da09ab319d70218
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592123"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="e77c6-102">Vorgehensweise: Überschreiben einer globalen Proxyauswahl</span><span class="sxs-lookup"><span data-stu-id="e77c6-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="e77c6-103">In diesem Beispiel wird an `www.contoso.com` eine **WebRequest** gesendet, die die globale Proxyauswahl mit einem Proxyserver namens `alternateproxy` auf Port 80 überschreibt.</span><span class="sxs-lookup"><span data-stu-id="e77c6-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e77c6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e77c6-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e77c6-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e77c6-105">Compiling the Code</span></span>  
 <span data-ttu-id="e77c6-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e77c6-106">This example requires:</span></span>  
  
-   <span data-ttu-id="e77c6-107">[`using`-Anweisung](~/docs/csharp/language-reference/keywords/using-directive.md) für den **System.Net**-Namespace</span><span class="sxs-lookup"><span data-stu-id="e77c6-107">A [`using` directive](~/docs/csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e77c6-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e77c6-108">See also</span></span>
- [<span data-ttu-id="e77c6-109">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="e77c6-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
- [<span data-ttu-id="e77c6-110">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="e77c6-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
