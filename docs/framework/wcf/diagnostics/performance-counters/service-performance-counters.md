---
title: Dienst-Leistungsindikatoren
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: de51c6d0a3070f8bba8a2c77f9c028e7cfbc944d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="service-performance-counters"></a><span data-ttu-id="6bf5c-102">Dienst-Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="6bf5c-102">Service Performance Counters</span></span>
<span data-ttu-id="6bf5c-103">Mit Dienst-Leistungsindikatoren wird das Dienstverhalten insgesamt gemessen und die Leistung des gesamten Diensts geprüft.</span><span class="sxs-lookup"><span data-stu-id="6bf5c-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="6bf5c-104">Die Dienst-Leistungsindikatoren sind unter dem `ServiceModelService 4.0.0.0`-Leistungsobjekt zu finden, wenn sie im Leistungsmonitor (Perfmon.exe) angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6bf5c-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="6bf5c-105">Die Instanzen werden nach dem folgenden Schema benannt:</span><span class="sxs-lookup"><span data-stu-id="6bf5c-105">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  <span data-ttu-id="6bf5c-106">Es gibt eine Längenbeschränkung des Namens einer Leistungsindikatorinstanz.</span><span class="sxs-lookup"><span data-stu-id="6bf5c-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="6bf5c-107">Wenn ein [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Instanzname des Indikators die maximale Länge überschreitet, ersetzt [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] einen Teil des Instanznamens durch einen Hashwert.</span><span class="sxs-lookup"><span data-stu-id="6bf5c-107">When a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] counter instance name exceeds the maximum length, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bf5c-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bf5c-108">See Also</span></span>  
 [<span data-ttu-id="6bf5c-109">Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="6bf5c-109">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
