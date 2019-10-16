---
title: Dienst-Leistungsindikatoren
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: 929ddcb2f271b7488270ea39e7a3a0037158c855
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320025"
---
# <a name="service-performance-counters"></a><span data-ttu-id="1597d-102">Dienst-Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="1597d-102">Service Performance Counters</span></span>
<span data-ttu-id="1597d-103">Mit Dienst-Leistungsindikatoren wird das Dienstverhalten insgesamt gemessen und die Leistung des gesamten Diensts geprüft.</span><span class="sxs-lookup"><span data-stu-id="1597d-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="1597d-104">Die Dienst-Leistungsindikatoren sind unter dem `ServiceModelService 4.0.0.0`-Leistungsobjekt zu finden, wenn sie im Leistungsmonitor (Perfmon.exe) angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1597d-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="1597d-105">Die Instanzen werden nach dem folgenden Schema benannt:</span><span class="sxs-lookup"><span data-stu-id="1597d-105">The instances are named using the following pattern:</span></span>  
  
`ServiceName@ServiceBaseAddress`
  
> [!CAUTION]
> <span data-ttu-id="1597d-106">Es gibt eine Längenbeschränkung des Namens einer Leistungsindikatorinstanz.</span><span class="sxs-lookup"><span data-stu-id="1597d-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="1597d-107">Wenn der Name einer Windows Communication Foundation (WCF)-Leistungs Zählers die maximale Länge überschreitet, ersetzt WCF einen Teil des Instanznamens durch einen Hashwert.</span><span class="sxs-lookup"><span data-stu-id="1597d-107">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1597d-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1597d-108">See also</span></span>

- [<span data-ttu-id="1597d-109">Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="1597d-109">Performance Counters</span></span>](index.md)
