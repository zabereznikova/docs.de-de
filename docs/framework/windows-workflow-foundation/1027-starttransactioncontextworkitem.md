---
title: "1027 - StartTransactionContextWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1027 - StartTransactionContextWorkItem
## Eigenschaften  
  
|||  
|-|-|  
|ID|1027|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Ausführlich|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt an, dass ein TransactionContextWorkItem mit der Ausführung beginnt.  
  
## Meldung  
 Die Ausführung von TransactionContextWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|Aktivität|xs:string|Der Typname der Aktivität.|  
|DisplayName|xs:string|Der Anzeigename der Aktivität.|  
|InstanceId|xs:string|Die Instanz\-ID der Aktivität.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|