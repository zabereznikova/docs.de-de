---
title: "440 - StartSignpostEvent1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 440 - StartSignpostEvent1
## Eigenschaften  
  
|||  
|-|-|  
|ID|440|  
|Schlüsselwörter|Troubleshooting|  
|Grad|Informationen|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Gibt in der Aktivitätsablaufverfolgung eine Nachricht an, die das Überschreiten einer Aktivitätsgrenze beim Senden oder Empfangen gestartet hat.  
  
## Nachricht  
 Aktivitätsgrenze.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|ExtendedData|`xs:string`|Der Name der Aktivität.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|