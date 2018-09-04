---
title: Abgelehnte Nachrichten in der Warteschlange pro Sekunde
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 096e2188b13d0fd5a9be35e5e6473107a58c5566
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507279"
---
# <a name="queued-rejected-messages-per-second"></a>Abgelehnte Nachrichten in der Warteschlange pro Sekunde
Indikatorname: Queued Messages Rejected Per Second.  
  
## <a name="description"></a>Beschreibung  
 Die Anzahl der Meldungen, die vom Warteschlangentransport für diesen Dienst pro Sekunde abgelehnt werden.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
