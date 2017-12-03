---
title: 'Endpunkt: Calls Failed Per Second'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b41a1fba1c1630532524bb4d6bc759ec21e2865
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint-calls-failed-per-second"></a>Endpunkt: Calls Failed Per Second
Indikatorname: Calls Failed Per Second  
  
## <a name="description"></a>Beschreibung  
 Die Anzahl von Aufrufen, die nicht behandelte Ausnahmen aufweisen und von diesem Endpunkt in einer Sekunde empfangen werden.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)  
  
 Der Wert dieses Indikators erhöht sich, sobald an diesem Endpunkt eine nicht behandelte Ausnahme auftritt.  
  
## <a name="see-also"></a>Siehe auch  
 [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
