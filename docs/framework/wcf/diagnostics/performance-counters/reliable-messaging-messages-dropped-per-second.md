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
# <a name="reliable-messaging-messages-dropped-per-second"></a>Reliable Messaging Messages Dropped Per Second
Indikatorname: Reliable Messaging Sessions Dropped Per Second.  
  
## <a name="description"></a>Beschreibung  
 Gesamtzahl der zuverlässigen Messagingnachrichten, die pro Sekunde in diesem Dienst verworfen wurden.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
