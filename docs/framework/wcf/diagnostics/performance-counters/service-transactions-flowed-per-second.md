---
title: 'Dienst: Transaktionen Flowed Per Second'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: 2ed9f6711c998bbd3f1130b9a91d8ac850821a07
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559323"
---
# <a name="service-transactions-flowed-per-second"></a>Dienst: Transaktionen Flowed Per Second
Indikatorname: Transactions Flowed Per Second.  
  
## <a name="description"></a>BESCHREIBUNG  
 Anzahl der Transaktionen, die innerhalb einer Sekunde in Vorgänge in diesem Dienst übergegangen sind.  
  
 Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
