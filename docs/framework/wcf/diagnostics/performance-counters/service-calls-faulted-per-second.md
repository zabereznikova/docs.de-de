---
title: 'Dienst: Calls Faulted Per Second'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 94247356-2b29-4b50-b639-91ca8c1cf3a9
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5cf587102814c5bbd2a9c22d88db90f48fbf4da1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="service-calls-faulted-per-second"></a><span data-ttu-id="4eab5-102">Dienst: Calls Faulted Per Second</span><span class="sxs-lookup"><span data-stu-id="4eab5-102">Service: Calls Faulted Per Second</span></span>
<span data-ttu-id="4eab5-103">Zählername: Calls Faulted Per Second.</span><span class="sxs-lookup"><span data-stu-id="4eab5-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4eab5-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4eab5-104">Description</span></span>  
 <span data-ttu-id="4eab5-105">Die Anzahl der Aufrufe, die in einer Sekunde an diesen Dienst Fehler zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="4eab5-105">Number of calls that have returned faults to this service in a second.</span></span>  
  
 <span data-ttu-id="4eab5-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="4eab5-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="4eab5-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="4eab5-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="4eab5-108">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Anwendungen übermitteln Dienstmethoden Informationen zu Verarbeitungsfehlern mithilfe von SOAP-Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="4eab5-108">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="4eab5-109">SOAP-Fehler sind Meldungstypen, die in den Metadaten für einen Dienstvorgang enthalten sind und daher einen Fehlervertrag erstellen, den Clients nutzen können, um ihre Ausführung robuster oder interaktiver zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="4eab5-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="4eab5-110">Da SOAP-Fehler gegenüber Clients in XML-Form ausgedrückt werden, sind sie sehr interoperabel.</span><span class="sxs-lookup"><span data-stu-id="4eab5-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eab5-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4eab5-111">See Also</span></span>  
 [<span data-ttu-id="4eab5-112">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="4eab5-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
