---
title: "Endpunkt: Fehlerhafte zuverlässige Messagingsitzungen pro Sekunde"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e3a63ba266de8cb4debd8ea43704f9b38049482c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a><span data-ttu-id="8a22f-102">Endpunkt: Fehlerhafte zuverlässige Messagingsitzungen pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="8a22f-102">Reliable Messaging Sessions Faulted Per Second</span></span>
<span data-ttu-id="8a22f-103">Indikatorname: Reliable Messaging Sessions Faulted Per Second.</span><span class="sxs-lookup"><span data-stu-id="8a22f-103">Counter Name: Reliable Messaging Sessions Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8a22f-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a22f-104">Description</span></span>  
 <span data-ttu-id="8a22f-105">Fehlerhafte zuverlässige Messagingsitzungen pro Sekunde in diesem Dienst (Anzahl).</span><span class="sxs-lookup"><span data-stu-id="8a22f-105">Number of reliable messaging sessions that are faulted in this service in a second.</span></span>  
  
 <span data-ttu-id="8a22f-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="8a22f-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="8a22f-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="8a22f-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
