---
title: Abgebrochene abgewickelte Vorgänge pro Sekunde
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: 6369fea6def5ebb6b62274caed31d5fb63b3b0e1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500558"
---
# <a name="transacted-operations-aborted-per-second"></a>Abgebrochene abgewickelte Vorgänge pro Sekunde
Indikatorname: Abgebrochene abgewickelte Vorgänge pro Sekunde.  
  
## <a name="description"></a>Beschreibung  
 Anzahl der von in diesem Dienst abgebrochenen Transaktionsvorgänge pro Sekunde.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
