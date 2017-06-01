---
title: "Dienst: Aufrufe pro Sekunde | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Dienst: Aufrufe pro Sekunde
Indikatorname: Aufrufe pro Sekunde  
  
## Beschreibung  
 Die Anzahl der Aufrufe an diesen Dienst pro Sekunde.  
  
 Bei diesem Zähler handelt es sich um einen Leistungsindikator vom Typ [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\). Dabei gibt der Zähler \(N\) die Anzahl der im letzten Messintervall durchgeführten Operationen und der Nenner \(D\) die Anzahl der Ticks im letzten Messintervall an. F ist die Tickfrequenz.