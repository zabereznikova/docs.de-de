---
title: 'Gewusst wie: Registrieren eines benutzerdefinierten Protokolls mit WebRequest'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4fdb1188aeb7fd754ab21a268070830f55347441
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="6cebf-102">Gewusst wie: Registrieren eines benutzerdefinierten Protokolls mit WebRequest</span><span class="sxs-lookup"><span data-stu-id="6cebf-102">How to: Register a Custom Protocol Using WebRequest</span></span>
<span data-ttu-id="6cebf-103">In diesem Beispiel wird gezeigt, wie Sie eine protokollspezifische Klasse registrieren, die an anderer Stelle definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6cebf-103">This example shows how to register a protocol specific classthat is defined elsewhere.</span></span> <span data-ttu-id="6cebf-104">In diesem Beispiel stellt `CustomWebRequestCreator` das vom Benutzer implementierte Objekt dar, das die **Create**-Methode implementiert, die wiederum das `CustomWebRequest`-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6cebf-104">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="6cebf-105">Im Codebeispiel wird vorausgesetzt, dass Sie den `CustomWebRequest`-Code geschrieben haben, der das benutzerdefinierte Protokoll implementiert.</span><span class="sxs-lookup"><span data-stu-id="6cebf-105">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cebf-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6cebf-106">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6cebf-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6cebf-107">Compiling the Code</span></span>  
 <span data-ttu-id="6cebf-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6cebf-108">This example requires:</span></span>  
  
 <span data-ttu-id="6cebf-109">Verweise auf den Namespace <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="6cebf-109">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cebf-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6cebf-110">See Also</span></span>  
 [<span data-ttu-id="6cebf-111">Programmieren austauschbarer Protokolle</span><span class="sxs-lookup"><span data-stu-id="6cebf-111">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
