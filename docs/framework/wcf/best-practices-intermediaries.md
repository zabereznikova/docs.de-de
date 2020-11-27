---
title: 'Bewährte Methoden: Zwischenstufen'
ms.date: 03/30/2017
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
ms.openlocfilehash: 57be78681147dfc5bc37701a76c1347040f5da1f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96277893"
---
# <a name="best-practices-intermediaries"></a><span data-ttu-id="e6357-102">Bewährte Methoden: Zwischenstufen</span><span class="sxs-lookup"><span data-stu-id="e6357-102">Best Practices: Intermediaries</span></span>

<span data-ttu-id="e6357-103">Beim Aufrufen von Vermittlern müssen Fehler ordnungsgemäß behandelt werden, um sicherzustellen, dass dienstseitige Kanäle im Vermittler ordnungsgemäß geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="e6357-103">Care must be taken to handle faults correctly when calling intermediaries to make sure service side channels on the intermediary are closed properly.</span></span>  
  
 <span data-ttu-id="e6357-104">Stellen Sie sich folgendes Szenario vor:</span><span class="sxs-lookup"><span data-stu-id="e6357-104">Consider the following scenario.</span></span> <span data-ttu-id="e6357-105">Ein Client ruft einen Vermittler auf, der dann einen Back-End-Dienst aufruft.</span><span class="sxs-lookup"><span data-stu-id="e6357-105">A client makes a call to an intermediary which then calls a back-end service.</span></span>  <span data-ttu-id="e6357-106">Der Back-End-Dienst definiert keinen Fehlervertrag. Deshalb wird jeder von diesem Dienst ausgelöste Fehler als nicht typisierter Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="e6357-106">The back-end service defines no fault contract, so any fault thrown from that service will be treated as an un-typed fault.</span></span>  <span data-ttu-id="e6357-107">Der Back-End-Dienst löst einen aus, <xref:System.ApplicationException> und WCF bricht den Dienst seitigen Kanal ordnungsgemäß ab.</span><span class="sxs-lookup"><span data-stu-id="e6357-107">The back-end service throws an <xref:System.ApplicationException> and WCF correctly aborts the service-side channel.</span></span> <span data-ttu-id="e6357-108">Die <xref:System.ApplicationException> wird dann als <xref:System.ServiceModel.FaultException> für den Vermittler ausgelöste Ausnahme ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="e6357-108">The <xref:System.ApplicationException> then surfaces as a <xref:System.ServiceModel.FaultException> that is thrown to the intermediary.</span></span> <span data-ttu-id="e6357-109">Der Vermittler löst die <xref:System.ApplicationException> erneut aus.</span><span class="sxs-lookup"><span data-stu-id="e6357-109">The intermediary re-throws the <xref:System.ApplicationException>.</span></span> <span data-ttu-id="e6357-110">WCF interpretiert diese als nicht typisierten Fehler vom Vermittler und leitet den Fehler an den Client weiter.</span><span class="sxs-lookup"><span data-stu-id="e6357-110">WCF interprets this as an un-typed fault from the intermediary and forwards it on to the client.</span></span> <span data-ttu-id="e6357-111">Bei Empfang des Fehlers lösen der Vermittler und der Client Fehler für ihre clientseitigen Kanäle aus.</span><span class="sxs-lookup"><span data-stu-id="e6357-111">Upon receiving the fault, both the intermediary and the client fault their client-side channels.</span></span> <span data-ttu-id="e6357-112">Der dienstseitige Kanal des Vermittlers bleibt jedoch geöffnet, da WCF nicht weiß, ob es sich um einen schwerwiegenden Fehler handelt.</span><span class="sxs-lookup"><span data-stu-id="e6357-112">The intermediary’s service-side channel however remains open because WCF doesn’t know the fault is fatal.</span></span>  
  
 <span data-ttu-id="e6357-113">Für dieses Szenario wird empfohlen, zu bestimmen, ob der vom Dienst stammende Fehler schwerwiegend ist, und wenn er schwerwiegend ist, sollte der Vermittler einen Fehler für seinen dienstseitigen Kanal auslösen, wie im folgenden Codeausschnitt gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6357-113">The best practice in this scenario is to detect if the fault coming from the service is fatal and if so the intermediary should fault its service-side channel as shown in the following code snippet.</span></span>  
  
```csharp  
catch (Exception e)  
{  
    bool faulted = service.State == CommunicationState.Faulted;  
    service.Abort();  
    if (faulted)  
    {  
        throw new ApplicationException(e.Message);  
    }  
    else  
    {  
        throw;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6357-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e6357-114">See also</span></span>

- [<span data-ttu-id="e6357-115">WCF-Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="e6357-115">WCF Error Handling</span></span>](wcf-error-handling.md)
- [<span data-ttu-id="e6357-116">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="e6357-116">Specifying and Handling Faults in Contracts and Services</span></span>](specifying-and-handling-faults-in-contracts-and-services.md)
