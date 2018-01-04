---
title: Reliable Messaging Messages Dropped Per Second
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dbae9414c4ce5394fc0d4a83589e2e5e10ffcc8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="c4ed3-102">Reliable Messaging Messages Dropped Per Second</span><span class="sxs-lookup"><span data-stu-id="c4ed3-102">Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="c4ed3-103">Indikatorname: Reliable Messaging Sessions Dropped Per Second.</span><span class="sxs-lookup"><span data-stu-id="c4ed3-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c4ed3-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4ed3-104">Description</span></span>  
 <span data-ttu-id="c4ed3-105">Gesamtzahl der zuverlässigen Messagingnachrichten, die pro Sekunde in diesem Dienst verworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="c4ed3-105">Total number of reliable messaging messages that have been dropped in this service in a second.</span></span>  
  
 <span data-ttu-id="c4ed3-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="c4ed3-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="c4ed3-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="c4ed3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
