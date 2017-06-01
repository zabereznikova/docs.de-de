---
title: "Dienst: Calls Faulted Per Second | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 94247356-2b29-4b50-b639-91ca8c1cf3a9
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Dienst: Calls Faulted Per Second
Zählername: Calls Faulted Per Second.  
  
## Beschreibung  
 Die Anzahl der Aufrufe, die in einer Sekunde an diesen Dienst Fehler zurückgegeben haben.  
  
 Bei diesem Zähler handelt es sich um einen Leistungsindikator vom Typ [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:  
  
 \(N 1 \- N 0\)\/\(\(D 1 \- D 0\)\/F\)  
  
 In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Anwendungen übermitteln Dienstmethoden Informationen zu Verarbeitungsfehlern mithilfe von SOAP\-Fehlernachrichten.SOAP\-Fehler sind Meldungstypen, die in den Metadaten für einen Dienstvorgang enthalten sind und daher einen Fehlervertrag erstellen, den Clients nutzen können, um ihre Ausführung robuster oder interaktiver zu gestalten.Da SOAP\-Fehler gegenüber Clients in XML\-Form ausgedrückt werden, sind sie sehr interoperabel.  
  
## Siehe auch  
 [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)