---
title: "Besch&#228;digte Nachrichten in der Warteschlange pro Sekunde | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Besch&#228;digte Nachrichten in der Warteschlange pro Sekunde
Indikatorname: Queued Poison Messages Per Second.  
  
## Beschreibung  
 Die Anzahl der Nachrichten, die pro Sekunde durch den Warteschlangentransport für diesen Dienst als beschädigt gekennzeichnet wurden.  
  
 Bei diesem Zähler handelt es sich um einen Leistungsindikator vom Typ [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:  
  
 \(N 1 \- N 0\)\/\( \(D 1 \- D 0\)\/F\)