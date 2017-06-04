---
title: "3507 - ServiceEndpointAdded | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3507 - ServiceEndpointAdded
## Eigenschaften  
  
|||  
|-|-|  
|ID|3507|  
|Schlüsselwörter|WFServices|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Gibt an, dass ein Dienstendpunkt hinzugefügt wurde.  
  
## Meldung  
 Für Adresse '%1', Bindung '%2' und Vertrag '%3' wurde ein Dienstendpunkt hinzugefügt.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|Adresse|xs:string|Die Adresse des Endpunkts.|  
|Bindung|xs:string|Die Bindung des Endpunkts.|  
|Vertrag|xs:string|Der Vertrag des Endpunkts.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|