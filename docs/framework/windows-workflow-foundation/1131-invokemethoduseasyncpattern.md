---
title: "1131 - InvokeMethodUseAsyncPattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1131 - InvokeMethodUseAsyncPattern
## Eigenschaften  
  
|||  
|-|-|  
|ID|1131|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Während des CacheMetadata\-Schritts gibt die InvokeMethod\-Aktivität an, dass sie das asynchrone Muster für den Methodenaufruf verwendet.  
  
## Meldung  
 InvokeMethod '%1' \- Methode verwendet das asynchrone Muster von '%2' und '%3'.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|InvokeMethod|xs:string|Der Anzeigename der InvokeMethod\-Aktivität.|  
|BeginMethod|xs:string|Der Name der Anfangsmethode.|  
|EndMethod|xs:string|Der Name der Endmethode.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|