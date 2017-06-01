---
title: "1124 - InvokeMethodIsStatic | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b9643641-fb52-4fa8-b354-4dd6617d68f6
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1124 - InvokeMethodIsStatic
## Eigenschaften  
  
|||  
|-|-|  
|ID|1124|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Während des CacheMetadata\-Schritts gibt die InvokeMethod\-Aktivität an, dass die aufzurufende Methode statisch ist.  
  
## Meldung  
 InvokeMethod '%1' \- Methode ist statisch.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|InvokeMethod|xs:string|Der Anzeigename der InvokeMethod\-Aktivität.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|