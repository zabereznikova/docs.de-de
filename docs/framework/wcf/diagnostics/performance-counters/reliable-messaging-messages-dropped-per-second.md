---
title: Reliable Messaging Messages Dropped Per Second
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 7722b32f99b302c5c272e095033879c9e04c7ee1
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44075383"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="1b1be-102">Reliable Messaging Messages Dropped Per Second</span><span class="sxs-lookup"><span data-stu-id="1b1be-102">Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="1b1be-103">Indikatorname: Reliable Messaging Sessions Dropped Per Second.</span><span class="sxs-lookup"><span data-stu-id="1b1be-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1b1be-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b1be-104">Description</span></span>  
 <span data-ttu-id="1b1be-105">Gesamtzahl der zuverlässigen Messagingnachrichten, die pro Sekunde in diesem Dienst verworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="1b1be-105">Total number of reliable messaging messages that have been dropped in this service in a second.</span></span>  
  
 <span data-ttu-id="1b1be-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="1b1be-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="1b1be-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="1b1be-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
