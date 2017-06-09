---
title: "ActivityTransfer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# ActivityTransfer
Aktivitätsübertragungsereignis  
  
## Syntax  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## Methoden  
 Von der ActivityTransfer\-Klasse werden keine Methoden definiert.  
  
## Eigenschaften  
 Die ActivityTransfer\-Klasse besitzt folgende Eigenschaften:  
  
### ActivityID  
  
-   Datentyp: object                   
     Zugriffstyp: Schreibgeschützt  
  
-   Aktivitäts\-ID  
  
### RelatedActivityID  
  
-   Datentyp: object                   
     Zugriffstyp: Schreibgeschützt  
  
-   Verwandte Aktivitäts\-ID  
  
## Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|