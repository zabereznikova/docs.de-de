---
title: "1150 - CompensationState | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1150 - CompensationState
## Eigenschaften  
  
|||  
|-|-|  
|ID|1150|  
|Schlüsselwörter|WFActivities|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt eine Statusänderung in einer CompensableActivity an.  
  
## Meldung  
 CompensableActivity '%1' hat den Status '%2'.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|DisplayName|xs:string|Der Anzeigename der Aktivität.|  
|Zustand|xs:string|Der Kompensationsstatus.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|