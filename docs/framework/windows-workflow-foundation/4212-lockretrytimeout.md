---
title: "4212 - LockRetryTimeout | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4212 - LockRetryTimeout
## Eigenschaften  
  
|||  
|-|-|  
|ID|4212|  
|Schlüsselwörter|WFInstanceStore|  
|Ebene|Warnung|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Im SQL\-Anbieter ist ein Timeout aufgetreten bei dem Versuch, die Instanzsperre abzurufen.  
  
## Meldung  
 Timeout beim Versuch, die Instanzsperre abzurufen. Der Vorgang wurde nicht innerhalb des zugewiesenen Timeouts von %1 abgeschlossen.  Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|Delay|xs:string|Die Verzögerung zwischen den Wiederholungen.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|