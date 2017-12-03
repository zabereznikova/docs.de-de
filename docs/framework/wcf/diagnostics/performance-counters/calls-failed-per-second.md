---
title: Fehlerhafte Aufrufe pro Sekunde
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 876932c707a30d25e6ee6d9abf8e3510dcd13f65
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="calls-failed-per-second"></a>Fehlerhafte Aufrufe pro Sekunde
Zählername: Fehlerhafte Aufrufe pro Sekunde  
  
## <a name="description"></a>Beschreibung  
 Anzahl von Aufrufen mit nicht behandelten Ausnahmen in diesem Vorgang innerhalb einer Sekunde.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)  
  
 Der Wert dieses Zählers erhöht sich, sobald in diesem Vorgang eine nicht behandelte Ausnahme auftritt.  
  
## <a name="see-also"></a>Siehe auch  
 [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
