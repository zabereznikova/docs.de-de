---
title: 'Dienst: Fehlerhafte Anrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: c97e4b0c6c2c71756a9bed7b1a2359ad0c118a98
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252971"
---
# <a name="service-calls-failed-per-second"></a>Dienst: Fehlerhafte Anrufe pro Sekunde

Indikatorname: Calls Failed Per Second  
  
## <a name="description"></a>BESCHREIBUNG  

 Die Anzahl von Aufrufen, die nicht behandelte Ausnahmen aufweisen und von diesem Dienst in einer Sekunde empfangen werden.  
  
 Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)  
  
 In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.  
  
 In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.  
  
 Der Wert dieses Indikators erhöht sich jedes Mal, wenn in diesem Dienst eine nicht behandelte Ausnahme auftritt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../specifying-and-handling-faults-in-contracts-and-services.md)
