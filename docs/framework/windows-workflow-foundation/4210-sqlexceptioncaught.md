---
title: "4210 - SqlExceptionCaught | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f0ce8af3-eb4c-48c8-b3d9-dd2f94b5574b
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4210 - SqlExceptionCaught
## Eigenschaften  
  
|||  
|-|-|  
|ID|4210|  
|Schlüsselwörter|WFInstanceStore|  
|Ebene|Warnung|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt an, dass eine SQL\-Ausnahme abgefangen wurde.  
  
## Meldung  
 SQL\-Ausnahme Nummer %1, Nachricht %2 wurde aufgefangen.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|ErrorNumber|xs:string|Die SQL\-Fehlernummer.|  
|ExceptionMessage|xs:string|Die Nachricht aus der SQL\-Ausnahme.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|