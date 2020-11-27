---
title: Calls Faulted Per Second
ms.date: 03/30/2017
ms.assetid: 81c88073-8e32-4520-a71a-2c56b71ee515
ms.openlocfilehash: 0e69cadfdbb4e387382ba33aa9cf977e4cdb9c08
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271420"
---
# <a name="calls-faulted-per-second"></a><span data-ttu-id="e5ee1-102">Calls Faulted Per Second</span><span class="sxs-lookup"><span data-stu-id="e5ee1-102">Calls Faulted Per Second</span></span>

<span data-ttu-id="e5ee1-103">Indikatorname: Calls Faulted Per Second</span><span class="sxs-lookup"><span data-stu-id="e5ee1-103">Counter Name: Calls Faulted Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="e5ee1-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e5ee1-104">Description</span></span>  

 <span data-ttu-id="e5ee1-105">Die Anzahl der Aufrufe, die in einer Sekunde an diesen Vorgang Fehler zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="e5ee1-105">Number of calls that returned faults to this operation in a second.</span></span>  
  
 <span data-ttu-id="e5ee1-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="e5ee1-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="e5ee1-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="e5ee1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="e5ee1-108">In Windows Communication Foundation (WCF)-Anwendungen übermitteln Dienst Methoden Verarbeitungsfehler Informationen mithilfe von SOAP-Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="e5ee1-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="e5ee1-109">SOAP-Fehler sind Meldungstypen, die in den Metadaten für einen Dienstvorgang enthalten sind und daher einen Fehlervertrag erstellen, den Clients nutzen können, um ihre Ausführung robuster oder interaktiver zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="e5ee1-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="e5ee1-110">Da SOAP-Fehler gegenüber Clients in XML-Form ausgedrückt werden, sind sie sehr interoperabel.</span><span class="sxs-lookup"><span data-stu-id="e5ee1-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5ee1-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e5ee1-111">See also</span></span>

- [<span data-ttu-id="e5ee1-112">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="e5ee1-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
