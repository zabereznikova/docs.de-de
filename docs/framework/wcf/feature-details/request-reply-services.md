---
title: Anforderung-Antwort-Dienste
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], request-reply services
- contracts [WCF], request-reply services
- WCF [WCF], request-reply services
- request-reply contracts [WCF]
ms.assetid: 2fa710f1-47f4-4598-b063-3ab3bd22ebba
ms.openlocfilehash: 10b82e859369dae4f57e0e13782e2375a304ab02
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295521"
---
# <a name="request-reply-services"></a><span data-ttu-id="32e2e-102">Anforderung-Antwort-Dienste</span><span class="sxs-lookup"><span data-stu-id="32e2e-102">Request-Reply Services</span></span>

<span data-ttu-id="32e2e-103">Anforderung-Antwort-Dienste sind der Standardtyp des Vorgangs Vertrags in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="32e2e-103">Request-reply services are the default type of operation contract in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="32e2e-104">Clients machen Aufrufe zu Dienstvorgängen und warten auf eine Antwort vom Dienst.</span><span class="sxs-lookup"><span data-stu-id="32e2e-104">Clients make calls to service operations and wait for a response from the service.</span></span> <span data-ttu-id="32e2e-105">Sie können Aufrufe zu einem Dienstvorgang entweder synchron vornehmen, wobei der Client sperrt, bis er eine Antwort vom Dienst oder die Aufrufzeiten erhält, oder asynchron, wobei der Client einen Aufruf zum Dienstvorgang startet, seine Arbeit weiter fortsetzt und die Antwort vom Dienst auf einem anderen Thread erhält.</span><span class="sxs-lookup"><span data-stu-id="32e2e-105">You can perform calls to a service operation either synchronously, where the client blocks until it receives a response from the service or the call times, or asynchronously, where the client makes a call to the service operation, continues working, and receives the response from the service on another thread.</span></span>  
  
 <span data-ttu-id="32e2e-106">Um einen Anforderung-Antwort-Dienstvertrag zu erstellen, definieren Sie Ihren Dienstvertrag, und wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse, wie im folgenden Beispielcode gezeigt, auf alle Vorgänge an.</span><span class="sxs-lookup"><span data-stu-id="32e2e-106">To create a request-reply service contract, define your service contract, and apply the <xref:System.ServiceModel.OperationContractAttribute> class to each operation, as shown in the following sample code.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="32e2e-107">Sie müssen die <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Eigenschaft nicht auf `false` festlegen, da dies das Standardverhalten ist.</span><span class="sxs-lookup"><span data-stu-id="32e2e-107">You do not have to set the  <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `false` because this is the default behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32e2e-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32e2e-108">See also</span></span>

- [<span data-ttu-id="32e2e-109">Unidirektionale Dienste</span><span class="sxs-lookup"><span data-stu-id="32e2e-109">One-Way Services</span></span>](one-way-services.md)
- [<span data-ttu-id="32e2e-110">Duplexdienste</span><span class="sxs-lookup"><span data-stu-id="32e2e-110">Duplex Services</span></span>](duplex-services.md)
