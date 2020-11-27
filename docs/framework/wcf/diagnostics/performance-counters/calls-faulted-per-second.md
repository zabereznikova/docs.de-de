---
title: Calls Faulted Per Second
ms.date: 03/30/2017
ms.assetid: 81c88073-8e32-4520-a71a-2c56b71ee515
ms.openlocfilehash: 0e69cadfdbb4e387382ba33aa9cf977e4cdb9c08
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271420"
---
# <a name="calls-faulted-per-second"></a>Calls Faulted Per Second

Indikatorname: Calls Faulted Per Second  
  
## <a name="description"></a>BESCHREIBUNG  

 Die Anzahl der Aufrufe, die in einer Sekunde an diesen Vorgang Fehler zurückgegeben haben.  
  
 Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)  
  
 In Windows Communication Foundation (WCF)-Anwendungen übermitteln Dienst Methoden Verarbeitungsfehler Informationen mithilfe von SOAP-Fehlermeldungen. SOAP-Fehler sind Meldungstypen, die in den Metadaten für einen Dienstvorgang enthalten sind und daher einen Fehlervertrag erstellen, den Clients nutzen können, um ihre Ausführung robuster oder interaktiver zu gestalten. Da SOAP-Fehler gegenüber Clients in XML-Form ausgedrückt werden, sind sie sehr interoperabel.  
  
## <a name="see-also"></a>Weitere Informationen

- [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../specifying-and-handling-faults-in-contracts-and-services.md)
