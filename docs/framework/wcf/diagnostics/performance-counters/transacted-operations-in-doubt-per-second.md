---
title: Transacted Operations In Doubt Per Second
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: f7365c4e5f03711129916c8c6964f7e25e9b553e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416686"
---
# <a name="transacted-operations-in-doubt-per-second"></a>Transacted Operations In Doubt Per Second
Indikatorname: Transacted Operations In Doubt Per Second.  
  
## <a name="description"></a>Beschreibung  
 Anzahl von Transaktionsvorgängen mit einem zweifelhaften Ergebnis in diesem Dienst in einer Sekunde.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
