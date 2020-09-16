---
title: 'Dienst: Calls Faulted Per Second'
ms.date: 03/30/2017
ms.assetid: 94247356-2b29-4b50-b639-91ca8c1cf3a9
ms.openlocfilehash: 211240d5bef7fe31a36f636313b48a2b9e15b239
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556010"
---
# <a name="service-calls-faulted-per-second"></a><span data-ttu-id="0d548-102">Dienst: Calls Faulted Per Second</span><span class="sxs-lookup"><span data-stu-id="0d548-102">Service: Calls Faulted Per Second</span></span>
<span data-ttu-id="0d548-103">Zählername: Calls Faulted Per Second.</span><span class="sxs-lookup"><span data-stu-id="0d548-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0d548-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0d548-104">Description</span></span>  
 <span data-ttu-id="0d548-105">Die Anzahl der Aufrufe, die in einer Sekunde an diesen Dienst Fehler zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="0d548-105">Number of calls that have returned faults to this service in a second.</span></span>  
  
 <span data-ttu-id="0d548-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="0d548-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="0d548-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="0d548-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="0d548-108">In Windows Communication Foundation (WCF)-Anwendungen übermitteln Dienst Methoden Verarbeitungsfehler Informationen mithilfe von SOAP-Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="0d548-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="0d548-109">SOAP-Fehler sind Meldungstypen, die in den Metadaten für einen Dienstvorgang enthalten sind und daher einen Fehlervertrag erstellen, den Clients nutzen können, um ihre Ausführung robuster oder interaktiver zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="0d548-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="0d548-110">Da SOAP-Fehler gegenüber Clients in XML-Form ausgedrückt werden, sind sie sehr interoperabel.</span><span class="sxs-lookup"><span data-stu-id="0d548-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d548-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d548-111">See also</span></span>

- [<span data-ttu-id="0d548-112">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="0d548-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
