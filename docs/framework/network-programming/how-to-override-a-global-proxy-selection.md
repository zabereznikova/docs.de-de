---
title: 'Vorgehensweise: Überschreiben einer globalen Proxyauswahl'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 44845fb67aac4ff9ab9dda8cf4934153c8c4f23c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048273"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="01910-102">Vorgehensweise: Überschreiben einer globalen Proxyauswahl</span><span class="sxs-lookup"><span data-stu-id="01910-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="01910-103">In diesem Beispiel wird an `www.contoso.com` eine **WebRequest** gesendet, die die globale Proxyauswahl mit einem Proxyserver namens `alternateproxy` auf Port 80 überschreibt.</span><span class="sxs-lookup"><span data-stu-id="01910-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01910-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="01910-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="01910-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="01910-105">Compiling the Code</span></span>  
 <span data-ttu-id="01910-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="01910-106">This example requires:</span></span>  
  
- <span data-ttu-id="01910-107">[`using`-Anweisung](../../csharp/language-reference/keywords/using-directive.md) für den **System.Net**-Namespace</span><span class="sxs-lookup"><span data-stu-id="01910-107">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01910-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01910-108">See also</span></span>

- [<span data-ttu-id="01910-109">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="01910-109">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="01910-110">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="01910-110">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
