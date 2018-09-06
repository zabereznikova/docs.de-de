---
title: 'Dienst: Transaktionen Flowed Per Second'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: cb41abe74568c3e9641443b81fce3fb6eb6e41bf
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43874936"
---
# <a name="service-transactions-flowed-per-second"></a>Dienst: Transaktionen Flowed Per Second
Indikatorname: Transaktionen Flowed Per Second.  
  
## <a name="description"></a>Beschreibung  
 Anzahl der Transaktionen, die innerhalb einer Sekunde in Vorgänge in diesem Dienst übergegangen sind.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
