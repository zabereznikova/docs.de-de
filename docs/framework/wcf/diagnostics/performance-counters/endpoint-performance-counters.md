---
title: Endpunktleistungsindikatoren
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: 8354cff600f8c16a5ab9b4f6efd3c0b93a46276c
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803136"
---
# <a name="endpoint-performance-counters"></a><span data-ttu-id="680ae-102">Endpunktleistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="680ae-102">Endpoint Performance Counters</span></span>
<span data-ttu-id="680ae-103">Endpunktleistungsindikatoren zeichnen Daten auf, die zeigen, wie ein Endpunkt Nachrichten annimmt.</span><span class="sxs-lookup"><span data-stu-id="680ae-103">Endpoint performance counters capture data that reveals how an endpoint is accepting messages.</span></span> <span data-ttu-id="680ae-104">Sie sind beim Anzeigen mit dem Systemmonitor unter dem `ServiceModelEndpoint 4.0.0.0`-Leistungsobjekt zu finden.</span><span class="sxs-lookup"><span data-stu-id="680ae-104">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="680ae-105">Die Instanzen werden mithilfe des folgenden Musters benannt:</span><span class="sxs-lookup"><span data-stu-id="680ae-105">The instances are named using this pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="680ae-106">Die Daten ähneln denen, die für einzelne Vorgänge erfasst werden, sie werden jedoch nur über den Endpunkt aggregiert.</span><span class="sxs-lookup"><span data-stu-id="680ae-106">The data is similar to that collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="680ae-107">Es gibt eine Längenbeschränkung des Namens einer Leistungsindikatorinstanz.</span><span class="sxs-lookup"><span data-stu-id="680ae-107">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="680ae-108">Ein Windows Communication Foundation (WCF)--Instanzname die maximale Länge überschreitet, ersetzt WCF einen Teil des Instanznamens durch einen Hashwert.</span><span class="sxs-lookup"><span data-stu-id="680ae-108">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="680ae-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="680ae-109">See Also</span></span>  
 [<span data-ttu-id="680ae-110">Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="680ae-110">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
