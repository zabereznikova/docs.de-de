---
title: "Vorgangsleistungsindikatoren | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Vorgangsleistungsindikatoren
Vorgangsleistungsindikatoren befinden sich unter dem `ServiceModelOperation 4.0.0.0`\-Leistungsobjekt, wenn sie mit dem Leistungsmonitor \(Perfmon.exe\) angezeigt werden.Jeder Vorgang hat eine einzelne Instanz.Das heißt, wenn ein bestimmter Vertrag 10 Vorgänge enthält, werden mit diesem Vertrag 10 Vorgangsleistungsindikatoren verbunden.Die Objektinstanzen werden nach dem folgenden Muster benannt:  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 Mit diesem Indikator können Sie messen, wie der Aufruf verwendet wird und wie gut der Vorgang funktioniert.  
  
> [!CAUTION]
>  Es gibt eine Längenbeschränkung des Namens einer Leistungsindikatorinstanz.Wenn ein [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Instanzname des Indikators die maximale Länge überschreitet, ersetzt [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] einen Teil des Instanznamens durch einen Hashwert.  
  
## Siehe auch  
 [Leistungsindikatoren](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)