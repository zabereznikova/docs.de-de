---
title: 'Vorgehensweise: Registrieren eines benutzerdefinierten Protokolls mit WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: 5c9a81fc61a2272056ba34fa387fdafee6203824
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079499"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="d840a-102">Vorgehensweise: Registrieren eines benutzerdefinierten Protokolls mit WebRequest</span><span class="sxs-lookup"><span data-stu-id="d840a-102">How to: Register a Custom Protocol Using WebRequest</span></span>
<span data-ttu-id="d840a-103">In diesem Beispiel wird gezeigt, wie Sie eine protokollspezifische Klasse registrieren, die an anderer Stelle definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d840a-103">This example shows how to register a protocol specific class that is defined elsewhere.</span></span> <span data-ttu-id="d840a-104">In diesem Beispiel stellt `CustomWebRequestCreator` das vom Benutzer implementierte Objekt dar, das die **Create**-Methode implementiert, die wiederum das `CustomWebRequest`-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d840a-104">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="d840a-105">Im Codebeispiel wird vorausgesetzt, dass Sie den `CustomWebRequest`-Code geschrieben haben, der das benutzerdefinierte Protokoll implementiert.</span><span class="sxs-lookup"><span data-stu-id="d840a-105">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d840a-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d840a-106">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d840a-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d840a-107">Compiling the Code</span></span>  
 <span data-ttu-id="d840a-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d840a-108">This example requires:</span></span>  
  
 <span data-ttu-id="d840a-109">Verweise auf den Namespace <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="d840a-109">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d840a-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d840a-110">See also</span></span>

- [<span data-ttu-id="d840a-111">Programmieren austauschbarer Protokolle</span><span class="sxs-lookup"><span data-stu-id="d840a-111">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
