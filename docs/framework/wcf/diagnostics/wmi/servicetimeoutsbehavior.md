---
title: "ServiceTimeoutsBehavior | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# ServiceTimeoutsBehavior
ServiceTimeoutsBehavior  
  
## Syntax  
  
```  
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## Methoden  
 Die ServiceTimeoutsBehavior\-Klasse definiert keine Methoden.  
  
## Eigenschaften  
 Die ServiceTimeoutsBehavior\-Klasse verfügt über die folgende Eigenschaft:  
  
### TransactionTimeout  
 Datentyp: datetime \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Zeitraum, in dem eine Transaktion abgeschlossen werden muss.  
  
## Voraussetzungen  
  
|MOF|Deklariert in Servicemodel.mof|  
|---------|------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>