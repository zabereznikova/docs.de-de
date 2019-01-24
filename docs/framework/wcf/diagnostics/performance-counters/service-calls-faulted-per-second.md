---
title: 'Dienst: Calls Faulted Per Second'
ms.date: 03/30/2017
ms.assetid: 94247356-2b29-4b50-b639-91ca8c1cf3a9
ms.openlocfilehash: c9af93c7cc0f07ced4435c98fd307e7a7976687f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580082"
---
# <a name="service-calls-faulted-per-second"></a><span data-ttu-id="65700-102">Dienst: Calls Faulted Per Second</span><span class="sxs-lookup"><span data-stu-id="65700-102">Service: Calls Faulted Per Second</span></span>
<span data-ttu-id="65700-103">Indikatorname: Fehlerhafte Aufrufe pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="65700-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="65700-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65700-104">Description</span></span>  
 <span data-ttu-id="65700-105">Die Anzahl der Aufrufe, die in einer Sekunde an diesen Dienst Fehler zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="65700-105">Number of calls that have returned faults to this service in a second.</span></span>  
  
 <span data-ttu-id="65700-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="65700-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="65700-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="65700-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="65700-108">In Windows Communication Foundation (WCF)-Anwendungen kommunizieren Dienstmethoden Verarbeitung Fehlerinformationen mit SOAP-Fehlernachrichten.</span><span class="sxs-lookup"><span data-stu-id="65700-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="65700-109">SOAP-Fehler sind Meldungstypen, die in den Metadaten für einen Dienstvorgang enthalten sind und daher einen Fehlervertrag erstellen, den Clients nutzen können, um ihre Ausführung robuster oder interaktiver zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="65700-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="65700-110">Da SOAP-Fehler gegenüber Clients in XML-Form ausgedrückt werden, sind sie sehr interoperabel.</span><span class="sxs-lookup"><span data-stu-id="65700-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65700-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65700-111">See also</span></span>
- [<span data-ttu-id="65700-112">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="65700-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
