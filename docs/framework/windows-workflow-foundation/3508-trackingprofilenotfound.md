---
title: "3508 - TrackingProfileNotFound | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3508 - TrackingProfileNotFound
## Eigenschaften  
  
|||  
|-|-|  
|ID|3508|  
|Schlüsselwörter|WFServices|  
|Ebene|Ausführlich|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Gibt an, dass entweder das TrackingProfile nicht in der Konfigurationsdatei gefunden wurde oder die ActivityDefinitionId nicht übereinstimmt.  
  
## Meldung  
 TrackingProfile '%1' für die ActivityDefinitionId '%2' wurde nicht gefunden.  Entweder wurde das TrackingProfile nicht in der Konfigurationsdatei gefunden, oder die ActivityDefinitionId stimmt nicht überein.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|TrackingProfile|xs:string|Der Name des Nachverfolgungsprofils.|  
|ActivityDefinitionId|xs:string|Die Aktivitätsdefinitions\-ID.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|