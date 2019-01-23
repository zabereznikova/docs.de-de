---
title: 'Dienst: Fehlerhafte Aufrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: a043cf30fa67707aca3edf50cf23372ade5e5a42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559891"
---
# <a name="service-calls-failed-per-second"></a>Dienst: Fehlerhafte Aufrufe pro Sekunde
Indikatorname: Fehlerhafte Aufrufe pro Sekunde.  
  
## <a name="description"></a>Beschreibung  
 Die Anzahl von Aufrufen, die nicht behandelte Ausnahmen aufweisen und von diesem Dienst in einer Sekunde empfangen werden.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)  
  
 In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.  
  
 In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.  
  
 Der Wert dieses Indikators erhöht sich jedes Mal, wenn in diesem Dienst eine nicht behandelte Ausnahme auftritt.  
  
## <a name="see-also"></a>Siehe auch
- [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
