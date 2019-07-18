---
title: 'Dienst: Nicht autorisierte Sicherheitsaufrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
ms.openlocfilehash: 523e5182ca661e170e5cba01d5221b5c38251959
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773361"
---
# <a name="service-security-calls-not-authorized-per-second"></a>Dienst: Nicht autorisierte Sicherheitsaufrufe pro Sekunde
Indikatorname: Nicht autorisierte Sicherheitsaufrufe pro Sekunde  
  
## <a name="description"></a>Beschreibung  
 Anzahl der eingehenden Nachrichten in einer Sekunde, die von einem gültigen Benutzer stammen und ordnungsgemäß geschützt sind, wobei der Benutzer allerdings nicht für die Durchführung spezifischer Aufgaben autorisiert ist.  
  
 Dieser Indikator wird erhöht, wenn die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>-Methode `false` zurückgibt.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkId=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
