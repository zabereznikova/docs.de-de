---
title: Vorgangsleistungsindikatoren
ms.date: 03/30/2017
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
ms.openlocfilehash: 59c75dacb2a01f1b85d67d5cc1651dbc55b6aa8e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320166"
---
# <a name="operation-performance-counters"></a><span data-ttu-id="bcd64-102">Vorgangsleistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="bcd64-102">Operation Performance Counters</span></span>
<span data-ttu-id="bcd64-103">Vorgangsleistungsindikatoren befinden sich unter dem `ServiceModelOperation 4.0.0.0`-Leistungsobjekt, wenn sie mit dem Leistungsmonitor (Perfmon.exe) angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bcd64-103">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="bcd64-104">Jeder Vorgang hat eine einzelne Instanz.</span><span class="sxs-lookup"><span data-stu-id="bcd64-104">Each operation has an individual instance.</span></span> <span data-ttu-id="bcd64-105">Das heißt, wenn ein bestimmter Vertrag 10 Vorgänge enthält, werden mit diesem Vertrag 10 Vorgangsleistungsindikatoren verbunden.</span><span class="sxs-lookup"><span data-stu-id="bcd64-105">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="bcd64-106">Die Objektinstanzen werden nach dem folgenden Muster benannt:</span><span class="sxs-lookup"><span data-stu-id="bcd64-106">The object instances are named using the following pattern:</span></span>  
  
`(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)`
  
 <span data-ttu-id="bcd64-107">Mit diesem Indikator können Sie messen, wie der Aufruf verwendet wird und wie gut der Vorgang funktioniert.</span><span class="sxs-lookup"><span data-stu-id="bcd64-107">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="bcd64-108">Es gibt eine Längenbeschränkung des Namens einer Leistungsindikatorinstanz.</span><span class="sxs-lookup"><span data-stu-id="bcd64-108">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="bcd64-109">Wenn der Name einer Windows Communication Foundation (WCF)-Leistungs Zählers die maximale Länge überschreitet, ersetzt WCF einen Teil des Instanznamens durch einen Hashwert.</span><span class="sxs-lookup"><span data-stu-id="bcd64-109">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcd64-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcd64-110">See also</span></span>

- [<span data-ttu-id="bcd64-111">Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="bcd64-111">Performance Counters</span></span>](index.md)
