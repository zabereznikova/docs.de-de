---
title: "Endpunkt: Reliable Messaging Messages Dropped Per Second | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Endpunkt: Reliable Messaging Messages Dropped Per Second
Indikatorname: Reliable Messaging Sessions Dropped Per Second.  
  
## Beschreibung  
 Gesamtzahl der zuverlässigen Messagingnachrichten, die pro Sekunde an diesem Endpunkt verworfen wurden.  
  
 Bei diesem Zähler handelt es sich um einen Leistungsindikator vom Typ [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:  
  
 \(N 1 \- N 0\)\/\( \(D 1 \- D 0\)\/F\)