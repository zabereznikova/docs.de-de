---
title: Dienst-Leistungsindikatoren
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d2bc29ace454c6c41d3ad6ec11f98a9e6fb3e7d0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="service-performance-counters"></a>Dienst-Leistungsindikatoren
Mit Dienst-Leistungsindikatoren wird das Dienstverhalten insgesamt gemessen und die Leistung des gesamten Diensts geprüft. Die Dienst-Leistungsindikatoren sind unter dem `ServiceModelService 4.0.0.0`-Leistungsobjekt zu finden, wenn sie im Leistungsmonitor (Perfmon.exe) angezeigt werden. Die Instanzen werden nach dem folgenden Schema benannt:  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  Es gibt eine Längenbeschränkung des Namens einer Leistungsindikatorinstanz. Wenn ein [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Instanzname des Indikators die maximale Länge überschreitet, ersetzt [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] einen Teil des Instanznamens durch einen Hashwert.  
  
## <a name="see-also"></a>Siehe auch  
 [Leistungsindikatoren](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
