---
title: "3502 - InferredOperationDescription | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3502 - InferredOperationDescription
## Eigenschaften  
  
|||  
|-|-|  
|ID|3502|  
|Schlüsselwörter|WFServices|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Gibt an, dass eine OperationDescription aus WorkflowService abgeleitet wurde.  
  
## Meldung  
 Die OperationDescription mit Name\='%1' in Vertrag '%2' wurde aus WorkflowService abgeleitet.  IsOneWay\=%3.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|OperationName|xs:string|Der Name des Vorgangs.|  
|ContractName|xs:string|Der Name des Vertrags.|  
|IsOneWay|xs:string|True oder False gibt an, ob der Vertrag unidirektional ist.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|