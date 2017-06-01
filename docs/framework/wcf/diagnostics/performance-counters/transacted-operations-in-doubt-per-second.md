---
title: "Transacted Operations In Doubt Per Second | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Transacted Operations In Doubt Per Second
Indikatorname: Transacted Operations In Doubt Per Second.  
  
## Beschreibung  
 Anzahl von Transaktionsvorgängen mit einem zweifelhaften Ergebnis in diesem Dienst in einer Sekunde.  
  
 Bei diesem Zähler handelt es sich um einen Leistungsindikator vom Typ [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:  
  
 \(N 1 \- N 0\)\/\(\(D 1 \- D 0\)\/F\)