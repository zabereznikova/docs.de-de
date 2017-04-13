---
title: "&#220;bergegangene Transaktionen pro Sekunde | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &#220;bergegangene Transaktionen pro Sekunde
Indikatorname: Transactions Flowed Per Second  
  
## Beschreibung  
 Die Anzahl der in einer Sekunde an diesen Vorgang übergegangenen Transaktionen.  Dieser Indikator wird jeweils inkrementiert, wenn eine Transaktions\-ID in einer Nachricht enthalten ist, die an den Vorgang gesendet wird.  
  
 Bei diesem Zähler handelt es sich um einen Leistungsindikator vom Typ [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:  
  
 \(N 1 \- N 0\)\/\( \(D 1 \- D 0\)\/F\)