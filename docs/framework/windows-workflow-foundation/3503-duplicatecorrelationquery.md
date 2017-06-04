---
title: "3503 - DuplicateCorrelationQuery | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3503 - DuplicateCorrelationQuery
## Eigenschaften  
  
|||  
|-|-|  
|ID|3503|  
|Schlüsselwörter|WFServices|  
|Ebene|Warnung|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Gibt an, dass eine doppelte CorrelationQuery gefunden wurde.  Die doppelte Abfrage wird beim Berechnen von Korrelationen nicht verwendet.  
  
## Meldung  
 Es wurde eine doppelte CorrelationQuery mit Where\='%1' gefunden.  Diese doppelte Abfrage wird beim Berechnen von Korrelationen nicht verwendet.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|Where|xs:string|Where\-Abschnitt der Korrelationsabfrage.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|