---
title: 'Dienst: Aufrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: c23456f49eb867d5b6f66b4386a83615d95e07da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473927"
---
# <a name="service-calls-per-second"></a>Dienst: Aufrufe pro Sekunde
Indikatorname: Calls Per Second.  
  
## <a name="description"></a>Beschreibung  
 Die Anzahl der Aufrufe an diesen Dienst pro Sekunde.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F). Dabei gibt der Zähler (N) die Anzahl der im letzten Messintervall durchgeführten Operationen und der Nenner (D) die Anzahl der Ticks im letzten Messintervall an. F ist die Tickfrequenz.
