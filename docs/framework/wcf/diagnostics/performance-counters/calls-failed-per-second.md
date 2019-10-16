---
title: Fehlerhafte Aufrufe pro Sekunde
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: e7c0b53f4c2b1a7e87a5791b44e452ec9146c459
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321121"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="913ed-102">Fehlerhafte Aufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="913ed-102">Calls Failed Per Second</span></span>
<span data-ttu-id="913ed-103">Zählername: Fehlerhafte Aufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="913ed-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="913ed-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="913ed-104">Description</span></span>  
 <span data-ttu-id="913ed-105">Anzahl von Aufrufen mit nicht behandelten Ausnahmen in diesem Vorgang innerhalb einer Sekunde.</span><span class="sxs-lookup"><span data-stu-id="913ed-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="913ed-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="913ed-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="913ed-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="913ed-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="913ed-108">Dieser Wert wird jedes Mal inkrementiert, wenn in diesem Vorgang eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="913ed-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="913ed-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="913ed-109">See also</span></span>

- [<span data-ttu-id="913ed-110">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="913ed-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
