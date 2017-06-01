---
title: "AsymmetricSecurityBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# AsymmetricSecurityBindingElement
AsymmetricSecurityBindingElement  
  
## Syntax  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## Methoden  
 Die AsymmetricSecurityBindingElement\-Klasse definiert keine Methoden.  
  
## Eigenschaften  
 Die AsymmetricSecurityBindingElement\-Klasse verfügt über die folgenden Eigenschaften:  
  
### MessageProtectionOrder  
 Datentyp: Zeichenfolge  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Reihenfolge der Nachrichtenverschlüsselung und \-signatur für diese Bindung.  
  
### RequireSignatureConfirmation  
 Datentyp: Boolescher Wert  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob die Bindung eine Signaturbestätigung erfordert.  
  
## Voraussetzungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>