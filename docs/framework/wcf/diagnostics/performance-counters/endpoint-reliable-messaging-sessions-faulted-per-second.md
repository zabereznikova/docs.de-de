---
title: "Endpunkt: Reliable Messaging Sessions Faulted Per Second | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e9ae808a-7e1f-46b0-9560-d5a866be6d6e
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Endpunkt: Reliable Messaging Sessions Faulted Per Second
Indikatorname: Reliable Messaging Sessions Faulted Per Second.  
  
## Beschreibung  
 Anzahl der fehlerhaften zuverlässigen Messagingsitzungen an diesem Endpunkt \(pro Sekunde\).  
  
 Bei diesem Zähler handelt es sich um einen Leistungsindikator vom Typ [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:  
  
 \(N 1 \- N 0\)\/\( \(D 1 \- D 0\)\/F\)