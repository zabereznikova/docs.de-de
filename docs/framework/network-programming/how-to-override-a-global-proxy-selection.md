---
title: 'Vorgehensweise: Überschreiben einer globalen Proxyauswahl'
description: Verwenden Sie dieses Beispiel, um die globale Proxyauswahl zu überschreiben, indem Sie ein WebRequest-Anforderung an eine URL senden, die die Auswahl mit einem Proxyserver überschreibt.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 8931cdc471b957447277c333ba482a0cec0e6aa5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265738"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="885ca-103">Vorgehensweise: Überschreiben einer globalen Proxyauswahl</span><span class="sxs-lookup"><span data-stu-id="885ca-103">How to: Override a Global Proxy Selection</span></span>

<span data-ttu-id="885ca-104">In diesem Beispiel wird an `www.contoso.com` eine **WebRequest** gesendet, die die globale Proxyauswahl mit einem Proxyserver namens `alternateproxy` auf Port 80 überschreibt.</span><span class="sxs-lookup"><span data-stu-id="885ca-104">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="885ca-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="885ca-105">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="885ca-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="885ca-106">Compiling the Code</span></span>  

 <span data-ttu-id="885ca-107">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="885ca-107">This example requires:</span></span>  
  
- <span data-ttu-id="885ca-108">[`using`-Anweisung](../../csharp/language-reference/keywords/using-directive.md) für den **System.Net**-Namespace</span><span class="sxs-lookup"><span data-stu-id="885ca-108">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="885ca-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="885ca-109">See also</span></span>

- [<span data-ttu-id="885ca-110">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="885ca-110">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="885ca-111">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="885ca-111">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
