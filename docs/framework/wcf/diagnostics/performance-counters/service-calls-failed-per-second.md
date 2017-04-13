---
title: "Dienst: Fehlerhafte Anrufe pro Sekunde | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Dienst: Fehlerhafte Anrufe pro Sekunde
Indikatorname: Calls Failed Per Second  
  
## Beschreibung  
 Die Anzahl von Aufrufen, die nicht behandelte Ausnahmen aufweisen und von diesem Dienst in einer Sekunde empfangen werden.  
  
 Bei diesem Zähler handelt es sich um einen Leistungsindikator vom Typ [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:  
  
 \(N 1 \- N 0\)\/\(\(D 1 \- D 0\)\/F\)  
  
 In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.  
  
 In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.  
  
 Der Wert dieses Indikators erhöht sich jedes Mal, wenn in diesem Dienst eine nicht behandelte Ausnahme auftritt.  
  
## Siehe auch  
 [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)