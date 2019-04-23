---
title: 'Dienst: Calls Faulted Per Second'
ms.date: 03/30/2017
ms.assetid: 94247356-2b29-4b50-b639-91ca8c1cf3a9
ms.openlocfilehash: 595b623d70bad82ea39ab3ef93fb5fd499268ff2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088475"
---
# <a name="service-calls-faulted-per-second"></a>Dienst: Calls Faulted Per Second
Indikatorname: Fehlerhafte Aufrufe pro Sekunde.  
  
## <a name="description"></a>Beschreibung  
 Die Anzahl der Aufrufe, die in einer Sekunde an diesen Dienst Fehler zurückgegeben haben.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)  
  
 In Windows Communication Foundation (WCF)-Anwendungen kommunizieren Dienstmethoden Verarbeitung Fehlerinformationen mit SOAP-Fehlernachrichten. SOAP-Fehler sind Meldungstypen, die in den Metadaten für einen Dienstvorgang enthalten sind und daher einen Fehlervertrag erstellen, den Clients nutzen können, um ihre Ausführung robuster oder interaktiver zu gestalten. Da SOAP-Fehler gegenüber Clients in XML-Form ausgedrückt werden, sind sie sehr interoperabel.  
  
## <a name="see-also"></a>Siehe auch

- [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
