---
title: "3557 - TransactedReceiveScopeEndCommitFailed | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3557 - TransactedReceiveScopeEndCommitFailed
## Eigenschaften  
  
|||  
|-|-|  
|ID|3557|  
|Schlüsselwörter|WFServices|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Gibt an, dass der Aufruf von EndCommit für eine CommittableTransaction eine TransactionException ausgelöst hat.  
  
## Meldung  
 Der Aufruf von EndCommit für die CommittableTransaction mit ID \= '%1' hat eine TransactionException mit der folgenden Meldung ausgelöst: '%2'.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|TransactionId|xs:string|Die ID der CommittableTransaction.|  
|Ausnahme|xs:string|Die Ausnahmedetails der Ausnahme.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|