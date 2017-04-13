---
title: "Dienst: Calls Faulted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6da7f100-3f61-4b3c-9409-fe1360829b8a
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Dienst: Calls Faulted
Indikatorname: Aufrufe haben einen Fehler verursacht.  
  
## Beschreibung  
 Die Anzahl der Aufrufe dieses Diensts, die Fehler zurückgegeben haben.In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Anwendungen übermitteln Dienstmethoden Informationen über Verarbeitungsfehler mithilfe von SOAP\-Fehlernachrichten.SOAP\-Fehler sind Meldungstypen, die in den Metadaten für einen Dienstvorgang enthalten sind und daher einen Fehlervertrag erstellen, den Clients nutzen können, um ihre Ausführung robuster oder interaktiver zu gestalten.Da SOAP\-Fehler gegenüber Clients in XML\-Form ausgedrückt werden, sind sie sehr interoperabel.  
  
## Siehe auch  
 [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)