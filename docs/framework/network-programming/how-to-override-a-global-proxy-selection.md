---
title: 'Vorgehensweise: Überschreiben einer globalen Proxyauswahl'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: f822aa18b6eecaa1b1302ad6cc6b94f0b016e330
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127373"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="8033c-102">Vorgehensweise: Überschreiben einer globalen Proxyauswahl</span><span class="sxs-lookup"><span data-stu-id="8033c-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="8033c-103">In diesem Beispiel wird an `www.contoso.com` eine **WebRequest** gesendet, die die globale Proxyauswahl mit einem Proxyserver namens `alternateproxy` auf Port 80 überschreibt.</span><span class="sxs-lookup"><span data-stu-id="8033c-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8033c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8033c-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8033c-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8033c-105">Compiling the Code</span></span>  
 <span data-ttu-id="8033c-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8033c-106">This example requires:</span></span>  
  
-   <span data-ttu-id="8033c-107">[`using`-Anweisung](~/docs/csharp/language-reference/keywords/using-directive.md) für den **System.Net**-Namespace</span><span class="sxs-lookup"><span data-stu-id="8033c-107">A [`using` directive](~/docs/csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8033c-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8033c-108">See also</span></span>

- [<span data-ttu-id="8033c-109">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="8033c-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
- [<span data-ttu-id="8033c-110">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="8033c-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
