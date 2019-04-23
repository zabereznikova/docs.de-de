---
title: 'Vorgehensweise: Aktivieren einer WebRequest-Klasse zur Verwendung eines Proxys für die Internetkommunikation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: a2179e767a0556f5223f2f4c1cc91708133120a5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103700"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="0cb2c-102">Vorgehensweise: Aktivieren einer WebRequest-Klasse zur Verwendung eines Proxys für die Internetkommunikation</span><span class="sxs-lookup"><span data-stu-id="0cb2c-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>
<span data-ttu-id="0cb2c-103">In diesem Beispiel wird eine globale Proxyinstanz erstellt, die es jedem <xref:System.Net.WebRequest> ermöglicht, einen Proxy zu verwenden, um mit dem Internet zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="0cb2c-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="0cb2c-104">Im Beispiel wird davon ausgegangen, dass der Proxyserver `webproxy` heißt und auf Port 80 kommuniziert, dem Standard-HTTP-Port.</span><span class="sxs-lookup"><span data-stu-id="0cb2c-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cb2c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0cb2c-105">Example</span></span>  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0cb2c-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0cb2c-106">Compiling the Code</span></span>  
 <span data-ttu-id="0cb2c-107">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0cb2c-107">This example requires:</span></span>  
  
-   <span data-ttu-id="0cb2c-108">[`using`-Anweisung](../../csharp/language-reference/keywords/using-directive.md) für den **System.Net**-Namespace</span><span class="sxs-lookup"><span data-stu-id="0cb2c-108">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cb2c-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cb2c-109">See also</span></span>

- [<span data-ttu-id="0cb2c-110">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="0cb2c-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
- [<span data-ttu-id="0cb2c-111">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="0cb2c-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
