---
title: 'Endpunkt: Fehlerhafte Aufrufe pro Sekunde'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9840fc0a-0e4d-4638-96fd-40e3ab9e4667
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4f52a0f0b44a788bd5c2d34c125e31884c2a9afb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-calls-faulted-per-second"></a>Endpunkt: Fehlerhafte Aufrufe pro Sekunde
Zählername: Calls Faulted Per Second.  
  
## <a name="description"></a>Beschreibung  
 Die Anzahl der Aufrufe, die in einer Sekunde an diesem Endpunkt Fehler zurückgegeben haben.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)  
  
 In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Anwendungen übermitteln Dienstmethoden Informationen zu Verarbeitungsfehlern mithilfe von SOAP-Fehlermeldungen. SOAP-Fehler sind Meldungstypen, die in den Metadaten für einen Dienstvorgang enthalten sind und daher einen Fehlervertrag erstellen, den Clients nutzen können, um ihre Ausführung robuster oder interaktiver zu gestalten. Da SOAP-Fehler gegenüber Clients in XML-Form ausgedrückt werden, sind sie sehr interoperabel.  
  
## <a name="see-also"></a>Siehe auch  
 [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
