---
title: 'Gewusst wie: Überschreiben einer globalen Proxyauswahl'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 244315b5df4200524685bc5b9fb75a0d7fd9b39e
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930827"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="bf6f4-102">Gewusst wie: Überschreiben einer globalen Proxyauswahl</span><span class="sxs-lookup"><span data-stu-id="bf6f4-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="bf6f4-103">In diesem Beispiel wird an `www.contoso.com` eine **WebRequest** gesendet, die die globale Proxyauswahl mit einem Proxyserver namens `alternateproxy` auf Port 80 überschreibt.</span><span class="sxs-lookup"><span data-stu-id="bf6f4-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf6f4-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf6f4-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bf6f4-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="bf6f4-105">Compiling the Code</span></span>  
 <span data-ttu-id="bf6f4-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bf6f4-106">This example requires:</span></span>  
  
-   <span data-ttu-id="bf6f4-107">[`using`-Anweisung](~/docs/csharp/language-reference/keywords/using-directive.md) für den **System.Net**-Namespace</span><span class="sxs-lookup"><span data-stu-id="bf6f4-107">A [`using` directive](~/docs/csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf6f4-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf6f4-108">See Also</span></span>  
 [<span data-ttu-id="bf6f4-109">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="bf6f4-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="bf6f4-110">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="bf6f4-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
