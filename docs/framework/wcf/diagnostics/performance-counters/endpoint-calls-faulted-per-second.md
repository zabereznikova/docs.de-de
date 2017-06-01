---
title: "Endpunkt: Fehlerhafte Aufrufe pro Sekunde | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9840fc0a-0e4d-4638-96fd-40e3ab9e4667
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Endpunkt: Fehlerhafte Aufrufe pro Sekunde
Zählername: Calls Faulted Per Second.  
  
## Beschreibung  
 Die Anzahl der Aufrufe, die in einer Sekunde an diesem Endpunkt Fehler zurückgegeben haben.  
  
 Bei diesem Zähler handelt es sich um einen Leistungsindikator vom Typ [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:  
  
 \(N 1 \- N 0\)\/\(\(D 1 \- D 0\)\/F\)  
  
 In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Anwendungen übermitteln Dienstmethoden Informationen zu Verarbeitungsfehlern mithilfe von SOAP\-Fehlernachrichten.SOAP\-Fehler sind Meldungstypen, die in den Metadaten für einen Dienstvorgang enthalten sind und daher einen Fehlervertrag erstellen, den Clients nutzen können, um ihre Ausführung robuster oder interaktiver zu gestalten.Da SOAP\-Fehler gegenüber Clients in XML\-Form ausgedrückt werden, sind sie sehr interoperabel.  
  
## Siehe auch  
 [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)