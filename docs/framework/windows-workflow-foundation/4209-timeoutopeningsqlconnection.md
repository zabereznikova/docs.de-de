---
title: "4209 - TimeoutOpeningSqlConnection | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4209 - TimeoutOpeningSqlConnection
## Eigenschaften  
  
|||  
|-|-|  
|ID|4209|  
|Schlüsselwörter|WFInstanceStore|  
|Ebene|Fehler|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt an, dass ein Timeout aufgetreten ist bei dem Versuch, eine SQL\-Verbindung zu öffnen.  
  
## Meldung  
 Timeout beim Versuch, eine SQL\-Verbindung zu öffnen.  Der Vorgang wurde nicht innerhalb des zugewiesenen Timeouts von %1 abgeschlossen.  Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|Timeout|xs:string|Der Timeoutwert zum Öffnen der SQL\-Verbindung.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|