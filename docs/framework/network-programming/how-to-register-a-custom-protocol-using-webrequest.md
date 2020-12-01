---
title: 'Gewusst wie: Registrieren eines benutzerdefinierten Protokolls mit WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: 86ad862dbff9f4a982eec27a6806bcbb6c16f3ae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255805"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="337a9-102">Gewusst wie: Registrieren eines benutzerdefinierten Protokolls mit WebRequest</span><span class="sxs-lookup"><span data-stu-id="337a9-102">How to: Register a Custom Protocol Using WebRequest</span></span>

<span data-ttu-id="337a9-103">In diesem Beispiel wird gezeigt, wie Sie eine protokollspezifische Klasse registrieren, die an anderer Stelle definiert ist.</span><span class="sxs-lookup"><span data-stu-id="337a9-103">This example shows how to register a protocol specific class that is defined elsewhere.</span></span> <span data-ttu-id="337a9-104">In diesem Beispiel stellt `CustomWebRequestCreator` das vom Benutzer implementierte Objekt dar, das die **Create**-Methode implementiert, die wiederum das `CustomWebRequest`-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="337a9-104">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="337a9-105">Im Codebeispiel wird vorausgesetzt, dass Sie den `CustomWebRequest`-Code geschrieben haben, der das benutzerdefinierte Protokoll implementiert.</span><span class="sxs-lookup"><span data-stu-id="337a9-105">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="337a9-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="337a9-106">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="337a9-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="337a9-107">Compiling the Code</span></span>  

 <span data-ttu-id="337a9-108">Dieses Beispiel erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="337a9-108">This example requires:</span></span>  
  
 <span data-ttu-id="337a9-109">Verweise auf den Namespace <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="337a9-109">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="337a9-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="337a9-110">See also</span></span>

- [<span data-ttu-id="337a9-111">Programming Pluggable Protocols (Programmieren austauschbarer Protokolle)</span><span class="sxs-lookup"><span data-stu-id="337a9-111">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)
