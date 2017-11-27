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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 06df77ae14dbe4980ae54cc09a0822f59731bf1c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="e942b-102">Reliable Messaging Messages Dropped Per Second</span><span class="sxs-lookup"><span data-stu-id="e942b-102">Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="e942b-103">Indikatorname: Reliable Messaging Sessions Dropped Per Second.</span><span class="sxs-lookup"><span data-stu-id="e942b-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e942b-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e942b-104">Description</span></span>  
 <span data-ttu-id="e942b-105">Gesamtzahl der zuverlässigen Messagingnachrichten, die pro Sekunde in diesem Dienst verworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="e942b-105">Total number of reliable messaging messages that have been dropped in this service in a second.</span></span>  
  
 <span data-ttu-id="e942b-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="e942b-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="e942b-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="e942b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
