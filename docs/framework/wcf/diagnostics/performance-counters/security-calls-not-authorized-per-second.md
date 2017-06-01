---
title: "Nicht autorisierte Sicherheitsaufrufe pro Sekunde | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# Nicht autorisierte Sicherheitsaufrufe pro Sekunde
Indikatorname: Nicht autorisierte Sicherheitsaufrufe pro Sekunde.  
  
## Beschreibung  
 Die Anzahl der Aufrufe, die in diesem Vorgang in einer Sekunde keine Autorisierung erhielten.  
  
 Dieser Indikator wird inkrementiert, wenn die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>\-Methode `false` zurückgibt.Er gibt an, dass die eingehende Nachricht von einem gültigen Benutzer stammt und ordnungsgemäß geschützt ist, der Benutzer jedoch nicht für die Durchführung spezifischer Aufgaben autorisiert ist.  
  
 Bei diesem Zähler handelt es sich um einen Leistungsindikator vom Typ [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:  
  
 \(N 1 \- N 0\)\/\(\(D 1 \- D 0\)\/F\)