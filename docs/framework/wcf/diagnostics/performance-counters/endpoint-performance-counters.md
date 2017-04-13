---
title: "Endpunktleistungsindikatoren | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Endpunktleistungsindikatoren
Endpunktleistungsindikatoren zeichnen Daten auf, die zeigen, wie ein Endpunkt Nachrichten annimmt.Sie sind beim Anzeigen mit dem Systemmonitor unter dem `ServiceModelEndpoint 4.0.0.0`\-Leistungsobjekt zu finden.Die Instanzen werden mithilfe des folgenden Musters benannt:  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 Die Daten ähneln denen, die für einzelne Vorgänge erfasst werden, sie werden jedoch nur über den Endpunkt aggregiert.  
  
> [!CAUTION]
>  Es gibt eine Längenbeschränkung des Namens einer Leistungsindikatorinstanz.Wenn ein [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Instanzname des Indikators die maximale Länge überschreitet, ersetzt [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] einen Teil des Instanznamens durch einen Hashwert.  
  
## Siehe auch  
 [Leistungsindikatoren](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)