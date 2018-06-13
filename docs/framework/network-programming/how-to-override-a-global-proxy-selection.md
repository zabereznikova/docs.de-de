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
ms.openlocfilehash: c10cff979a18d8e07a1e7089f96157e4c38f040e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393905"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="7d120-102">Gewusst wie: Überschreiben einer globalen Proxyauswahl</span><span class="sxs-lookup"><span data-stu-id="7d120-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="7d120-103">In diesem Beispiel wird an „www.contoso.com“ eine **WebRequest** gesendet, die die globale Proxyauswahl mit einem Proxyserver namens `alternateproxy` auf Port 80 überschreibt.</span><span class="sxs-lookup"><span data-stu-id="7d120-103">This example sends a **WebRequest** to www.contoso.com that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d120-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d120-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7d120-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="7d120-105">Compiling the Code</span></span>  
 <span data-ttu-id="7d120-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7d120-106">This example requires:</span></span>  
  
-   <span data-ttu-id="7d120-107">Verweise auf den Namespace **System.Net**</span><span class="sxs-lookup"><span data-stu-id="7d120-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d120-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d120-108">See Also</span></span>  
 [<span data-ttu-id="7d120-109">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="7d120-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="7d120-110">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="7d120-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
