---
title: Abgebrochene abgewickelte Vorgänge pro Sekunde
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: dacdf93f4610df9161134a41ece19fd2a18637c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474531"
---
# <a name="transacted-operations-aborted-per-second"></a>Abgebrochene abgewickelte Vorgänge pro Sekunde
Indikatorname: Abgebrochene abgewickelte Vorgänge pro Sekunde.  
  
## <a name="description"></a>Beschreibung  
 Anzahl der von in diesem Dienst abgebrochenen Transaktionsvorgänge pro Sekunde.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
