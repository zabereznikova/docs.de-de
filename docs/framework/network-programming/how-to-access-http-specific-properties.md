---
title: 'Vorgehensweise: Zugreifen auf HTTP-spezifische Eigenschaften'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8848c7e-f5c5-4d42-b86d-9951ff8f4146
ms.openlocfilehash: 107e57ca947012f5e2f65835d684f5e6068b3681
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176591"
---
# <a name="how-to-access-http-specific-properties"></a><span data-ttu-id="31a2a-102">Vorgehensweise: Zugreifen auf HTTP-spezifische Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="31a2a-102">How to: Access HTTP-Specific Properties</span></span>
<span data-ttu-id="31a2a-103">In diesem Beispiel wird gezeigt, wie das HTTP-Verhalten **Keep-Alive** deaktiviert und die Protokollversionsnummer vom Webserver erhalten werden kann.</span><span class="sxs-lookup"><span data-stu-id="31a2a-103">This sample shows how to turn off the HTTP **Keep-alive** behavior and get the protocol version number from the Web server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31a2a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="31a2a-104">Example</span></span>  
  
```vb  
Dim HttpWReq As HttpWebRequest= _  
    CType(WebRequest.Create("http://www.contoso.com"), HttpWebRequest)  
' Turn off connection keep-alives.  
HttpWReq.KeepAlive = False  
  
Dim HttpWResp As HttpWebResponse = _  
    CType(HttpWReq.GetResponse(), HttpWebResponse)  
  
' Get the HTTP protocol version number returned by the server.  
Dim ver As String = HttpWResp.ProtocolVersion.ToString()  
HttpWResp.Close()  
```  
  
```csharp  
HttpWebRequest HttpWReq =   
    (HttpWebRequest)WebRequest.Create("http://www.contoso.com");  
// Turn off connection keep-alives.  
HttpWReq.KeepAlive = false;  
  
HttpWebResponse HttpWResp = (HttpWebResponse)HttpWReq.GetResponse();  
  
// Get the HTTP protocol version number returned by the server.  
String ver = HttpWResp.ProtocolVersion.ToString();  
HttpWResp.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="31a2a-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="31a2a-105">Compiling the Code</span></span>  
 <span data-ttu-id="31a2a-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="31a2a-106">This example requires:</span></span>  
  
-   <span data-ttu-id="31a2a-107">Verweise auf den Namespace **System.Net**</span><span class="sxs-lookup"><span data-stu-id="31a2a-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31a2a-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31a2a-108">See also</span></span>

- [<span data-ttu-id="31a2a-109">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="31a2a-109">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="31a2a-110">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="31a2a-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
- [<span data-ttu-id="31a2a-111">HTTP</span><span class="sxs-lookup"><span data-stu-id="31a2a-111">HTTP</span></span>](../../../docs/framework/network-programming/http.md)
