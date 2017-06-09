---
title: "MustUnderstandBehavior | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# MustUnderstandBehavior
MustUnderstandBehavior  
  
## Syntax  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## Methoden  
 Die MustUnderstandBehavior\-Klasse definiert keine Methoden.  
  
## Eigenschaften  
 Die MustUnderstandBehavior\-Klasse hat die folgende Eigenschaft:  
  
### ValidateMustUnderstand  
 Datentyp: Boolescher Wert  
  
 Zugriffstyp: Schreibgeschützt  
  
 Wenn der Wert `true` festgelegt wurde, verursachen alle SOAP\-Header mit dem `MustUnderstand`\-Attribut, die nicht behandelt werden, die Ausgabe einer Ausnahme.  
  
## Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof|  
|---------|------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>