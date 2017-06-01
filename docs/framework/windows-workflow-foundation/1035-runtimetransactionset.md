---
title: "1035 - RuntimeTransactionSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1035 - RuntimeTransactionSet
## Eigenschaften  
  
|||  
|-|-|  
|ID|1035|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Ausführlich|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt an, dass eine Aktivität die Laufzeittransaktion festgelegt hat.  
  
## Meldung  
 Die Laufzeittransaktion wurde von der Aktivität '%1', DisplayName: '%2', InstanceId: '%3' festgelegt. Die Ausführung wurde für die Aktivität '%4', DisplayName: '%5', InstanceId: '%6' isoliert.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|Aktivität|xs:string|Der Typname der Aktivität.|  
|DisplayName|xs:string|Der Anzeigename der Aktivität.|  
|InstanceId|xs:string|Die Instanz\-ID der Aktivität.|  
|IsolatedActivity|xs:string|Der Typname der Aktivität, für die die Transaktion isoliert ist.|  
|IsolatedActivityDisplayName|xs:string|Der Anzeigename der Aktivität, für die die Transaktion isoliert ist.|  
|IsolatedActivityInstanceId|xs:string|Die Instanz\-ID der Aktivität, für die die Transaktion isoliert ist.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|