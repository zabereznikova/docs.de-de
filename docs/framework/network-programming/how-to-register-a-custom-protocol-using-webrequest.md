---
title: 'Vorgehensweise: Registrieren eines benutzerdefinierten Protokolls mit WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: d2056bee6c8847989556799511dfaea326dcdac1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669041"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="2b82f-102">Vorgehensweise: Registrieren eines benutzerdefinierten Protokolls mit WebRequest</span><span class="sxs-lookup"><span data-stu-id="2b82f-102">How to: Register a Custom Protocol Using WebRequest</span></span>
<span data-ttu-id="2b82f-103">In diesem Beispiel wird gezeigt, wie Sie eine protokollspezifische Klasse registrieren, die an anderer Stelle definiert ist.</span><span class="sxs-lookup"><span data-stu-id="2b82f-103">This example shows how to register a protocol specific class that is defined elsewhere.</span></span> <span data-ttu-id="2b82f-104">In diesem Beispiel stellt `CustomWebRequestCreator` das vom Benutzer implementierte Objekt dar, das die **Create**-Methode implementiert, die wiederum das `CustomWebRequest`-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2b82f-104">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="2b82f-105">Im Codebeispiel wird vorausgesetzt, dass Sie den `CustomWebRequest`-Code geschrieben haben, der das benutzerdefinierte Protokoll implementiert.</span><span class="sxs-lookup"><span data-stu-id="2b82f-105">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b82f-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b82f-106">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2b82f-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2b82f-107">Compiling the Code</span></span>  
 <span data-ttu-id="2b82f-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2b82f-108">This example requires:</span></span>  
  
 <span data-ttu-id="2b82f-109">Verweise auf den Namespace <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="2b82f-109">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b82f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b82f-110">See also</span></span>
- [<span data-ttu-id="2b82f-111">Programmieren austauschbarer Protokolle</span><span class="sxs-lookup"><span data-stu-id="2b82f-111">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
