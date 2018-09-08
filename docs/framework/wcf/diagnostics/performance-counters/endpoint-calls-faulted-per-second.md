---
title: 'Endpunkt: Fehlerhafte Aufrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 9840fc0a-0e4d-4638-96fd-40e3ab9e4667
ms.openlocfilehash: f1b2997a0f1e16c897fc319d1833313141f5c4bf
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44199595"
---
# <a name="endpoint-calls-faulted-per-second"></a><span data-ttu-id="ed71f-102">Endpunkt: Fehlerhafte Aufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="ed71f-102">Endpoint: Calls Faulted Per Second</span></span>
<span data-ttu-id="ed71f-103">Zählername: Calls Faulted Per Second.</span><span class="sxs-lookup"><span data-stu-id="ed71f-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ed71f-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed71f-104">Description</span></span>  
 <span data-ttu-id="ed71f-105">Die Anzahl der Aufrufe, die in einer Sekunde an diesem Endpunkt Fehler zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="ed71f-105">Number of calls that have returned faults to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="ed71f-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="ed71f-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="ed71f-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="ed71f-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="ed71f-108">In Windows Communication Foundation (WCF)-Anwendungen kommunizieren Dienstmethoden Verarbeitung Fehlerinformationen mit SOAP-Fehlernachrichten.</span><span class="sxs-lookup"><span data-stu-id="ed71f-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="ed71f-109">SOAP-Fehler sind Meldungstypen, die in den Metadaten für einen Dienstvorgang enthalten sind und daher einen Fehlervertrag erstellen, den Clients nutzen können, um ihre Ausführung robuster oder interaktiver zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="ed71f-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="ed71f-110">Da SOAP-Fehler gegenüber Clients in XML-Form ausgedrückt werden, sind sie sehr interoperabel.</span><span class="sxs-lookup"><span data-stu-id="ed71f-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed71f-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed71f-111">See Also</span></span>  
 [<span data-ttu-id="ed71f-112">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="ed71f-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
