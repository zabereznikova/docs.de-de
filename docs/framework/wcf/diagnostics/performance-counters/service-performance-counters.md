---
title: "Dienst-Leistungsindikatoren | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Dienst-Leistungsindikatoren
Mit Dienst\-Leistungsindikatoren wird das Dienstverhalten insgesamt gemessen und die Leistung des gesamten Diensts geprüft.Die Dienst\-Leistungsindikatoren sind unter dem `ServiceModelService 4.0.0.0`\-Leistungsobjekt zu finden, wenn sie im Leistungsmonitor \(Perfmon.exe\) angezeigt werden.Die Instanzen werden nach dem folgenden Schema benannt:  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  Es gibt eine Längenbeschränkung für den Namen einer Leistungsindikatorinstanz.Wenn ein [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Instanzname des Indikators die maximale Länge überschreitet, ersetzt [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] einen Teil des Instanznamens durch einen Hashwert.  
  
## Siehe auch  
 [Leistungsindikatoren](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)