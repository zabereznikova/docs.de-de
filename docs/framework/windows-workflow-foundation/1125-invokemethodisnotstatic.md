---
title: "1125 - InvokeMethodIsNotStatic | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1125 - InvokeMethodIsNotStatic
## Eigenschaften  
  
|||  
|-|-|  
|ID|1125|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Während des CacheMetadata\-Schritts gibt die InvokeMethod\-Aktivität an, dass die aufzurufende Methode nicht statisch ist.  
  
## Meldung  
 InvokeMethod '%1' \- Methode ist nicht statisch.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|InvokeMethod|xs:string|Der Anzeigename der InvokeMethod\-Aktivität.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|