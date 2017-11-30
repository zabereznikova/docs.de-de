---
title: Endpunktleistungsindikatoren
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8d34df7c70e0edeef831843d9afcb2db32422ebe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-performance-counters"></a><span data-ttu-id="1fb1e-102">Endpunktleistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="1fb1e-102">Endpoint Performance Counters</span></span>
<span data-ttu-id="1fb1e-103">Endpunktleistungsindikatoren zeichnen Daten auf, die zeigen, wie ein Endpunkt Nachrichten annimmt.</span><span class="sxs-lookup"><span data-stu-id="1fb1e-103">Endpoint performance counters capture data that reveals how an endpoint is accepting messages.</span></span> <span data-ttu-id="1fb1e-104">Sie sind beim Anzeigen mit dem Systemmonitor unter dem `ServiceModelEndpoint 4.0.0.0`-Leistungsobjekt zu finden.</span><span class="sxs-lookup"><span data-stu-id="1fb1e-104">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="1fb1e-105">Die Instanzen werden mithilfe des folgenden Musters benannt:</span><span class="sxs-lookup"><span data-stu-id="1fb1e-105">The instances are named using this pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="1fb1e-106">Die Daten ähneln denen, die für einzelne Vorgänge erfasst werden, sie werden jedoch nur über den Endpunkt aggregiert.</span><span class="sxs-lookup"><span data-stu-id="1fb1e-106">The data is similar to that collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="1fb1e-107">Es gibt eine Längenbeschränkung des Namens einer Leistungsindikatorinstanz.</span><span class="sxs-lookup"><span data-stu-id="1fb1e-107">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="1fb1e-108">Wenn ein [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Instanzname des Indikators die maximale Länge überschreitet, ersetzt [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] einen Teil des Instanznamens durch einen Hashwert.</span><span class="sxs-lookup"><span data-stu-id="1fb1e-108">When a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] counter instance name exceeds the maximum length, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fb1e-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1fb1e-109">See Also</span></span>  
 [<span data-ttu-id="1fb1e-110">Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="1fb1e-110">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
