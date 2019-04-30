---
title: Abgelehnte Nachrichten in der Warteschlange pro Sekunde
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 096e2188b13d0fd5a9be35e5e6473107a58c5566
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916187"
---
# <a name="queued-rejected-messages-per-second"></a>Abgelehnte Nachrichten in der Warteschlange pro Sekunde
Indikatorname: In der Warteschlange Nachrichten pro Sekunde abgelehnt.  
  
## <a name="description"></a>Beschreibung  
 Die Anzahl der Meldungen, die vom Warteschlangentransport für diesen Dienst pro Sekunde abgelehnt werden.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
