---
title: 'Dienst: Transaktionen Flowed Per Second'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: 1151117c8537d4a8eaa4de60d14e314b55ce82d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="service-transactions-flowed-per-second"></a>Dienst: Transaktionen Flowed Per Second
Indikatorname: Transaktionen Flowed Per Second.  
  
## <a name="description"></a>Beschreibung  
 Anzahl der Transaktionen, die innerhalb einer Sekunde in Vorgänge in diesem Dienst übergegangen sind.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
