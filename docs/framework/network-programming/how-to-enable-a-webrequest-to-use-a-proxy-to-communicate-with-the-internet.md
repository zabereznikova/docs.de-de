---
title: 'Gewusst wie: Aktivieren von WebRequest zur Verwendung eines Proxys für die Internetkommunikation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0f57869dfecce3e59d0a255a6201dd966bc407e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33396905"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="9ab78-102">Gewusst wie: Aktivieren von WebRequest zur Verwendung eines Proxys für die Internetkommunikation</span><span class="sxs-lookup"><span data-stu-id="9ab78-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>
<span data-ttu-id="9ab78-103">In diesem Beispiel wird eine globale Proxyinstanz erstellt, die es jedem <xref:System.Net.WebRequest> ermöglicht, einen Proxy zu verwenden, um mit dem Internet zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="9ab78-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="9ab78-104">Im Beispiel wird davon ausgegangen, dass der Proxyserver `webproxy` heißt und auf Port 80 kommuniziert, dem Standard-HTTP-Port.</span><span class="sxs-lookup"><span data-stu-id="9ab78-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ab78-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9ab78-105">Example</span></span>  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ab78-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9ab78-106">Compiling the Code</span></span>  
 <span data-ttu-id="9ab78-107">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9ab78-107">This example requires:</span></span>  
  
-   <span data-ttu-id="9ab78-108">Verweise auf den Namespace **System.Net**</span><span class="sxs-lookup"><span data-stu-id="9ab78-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab78-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ab78-109">See Also</span></span>  
 [<span data-ttu-id="9ab78-110">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="9ab78-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="9ab78-111">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="9ab78-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
