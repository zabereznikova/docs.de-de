---
title: 'Gewusst wie: Überschreiben einer globalen Proxyauswahl'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 44845fb67aac4ff9ab9dda8cf4934153c8c4f23c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048273"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="089fb-102">Gewusst wie: Überschreiben einer globalen Proxyauswahl</span><span class="sxs-lookup"><span data-stu-id="089fb-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="089fb-103">In diesem Beispiel wird an **eine**WebRequest`www.contoso.com` gesendet, die die globale Proxyauswahl mit einem Proxyserver namens `alternateproxy` auf Port 80 überschreibt.</span><span class="sxs-lookup"><span data-stu-id="089fb-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="089fb-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="089fb-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="089fb-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="089fb-105">Compiling the Code</span></span>  
 <span data-ttu-id="089fb-106">Dieses Beispiel erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="089fb-106">This example requires:</span></span>  
  
- <span data-ttu-id="089fb-107">[`using`-Anweisung](../../csharp/language-reference/keywords/using-directive.md) für den **System.Net**-Namespace</span><span class="sxs-lookup"><span data-stu-id="089fb-107">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="089fb-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="089fb-108">See also</span></span>

- [<span data-ttu-id="089fb-109">Using Application Protocols (Verwenden von Anwendungsprotokollen)</span><span class="sxs-lookup"><span data-stu-id="089fb-109">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="089fb-110">Accessing the Internet Through a Proxy (Zugreifen auf das Internet über einen Proxy)</span><span class="sxs-lookup"><span data-stu-id="089fb-110">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
