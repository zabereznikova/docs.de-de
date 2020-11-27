---
title: 'Endpunkt: Calls Failed Per Second'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 0aeafa3d273ae22d9bbfe5e3edbac80c6e4851bd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271252"
---
# <a name="endpoint-calls-failed-per-second"></a>Endpunkt: Calls Failed Per Second

Indikatorname: Calls Failed Per Second  
  
## <a name="description"></a>BESCHREIBUNG  

 Die Anzahl von Aufrufen, die nicht behandelte Ausnahmen aufweisen und von diesem Endpunkt in einer Sekunde empfangen werden.  
  
 Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)  
  
 Der Wert dieses Indikators erhöht sich, sobald an diesem Endpunkt eine nicht behandelte Ausnahme auftritt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../specifying-and-handling-faults-in-contracts-and-services.md)
