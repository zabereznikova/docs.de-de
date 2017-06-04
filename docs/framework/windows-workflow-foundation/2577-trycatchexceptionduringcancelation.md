---
title: "2577 - TryCatchExceptionDuringCancelation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 2577 - TryCatchExceptionDuringCancelation
## Eigenschaften  
  
|||  
|-|-|  
|ID|2577|  
|Schlüsselwörter|WFActivities|  
|Ebene|Warnung|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt an, dass eine untergeordnete Aktivität der TryCatch\-Aktivität während des Abbruchs eine Ausnahme ausgelöst hat.  
  
## Meldung  
 Eine untergeordnete Aktivität der TryCatch\-Aktivität '%1' hat während des Abbruchs eine Ausnahme ausgelöst.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|DisplayName|xs:string|Der Anzeigename der Aktivität.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|