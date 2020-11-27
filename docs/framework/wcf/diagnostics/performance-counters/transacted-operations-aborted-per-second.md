---
title: Abgebrochene abgewickelte Vorgänge pro Sekunde
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: 1a23420ca1521a11168a859eef61cb8861a144f9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250020"
---
# <a name="transacted-operations-aborted-per-second"></a><span data-ttu-id="7425a-102">Abgebrochene abgewickelte Vorgänge pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="7425a-102">Transacted Operations Aborted Per Second</span></span>

<span data-ttu-id="7425a-103">Indikatorname: Abgebrochene abgewickelte Vorgänge pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="7425a-103">Counter Name: Transacted Operations Aborted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7425a-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7425a-104">Description</span></span>  

 <span data-ttu-id="7425a-105">Anzahl der von in diesem Dienst abgebrochenen Transaktionsvorgänge pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="7425a-105">Number of transactional operations that have been aborted in this service in a second.</span></span>  
  
 <span data-ttu-id="7425a-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="7425a-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="7425a-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="7425a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
