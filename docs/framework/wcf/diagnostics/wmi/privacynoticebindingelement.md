---
title: "PrivacyNoticeBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# PrivacyNoticeBindingElement
PrivacyNoticeBindingElement  
  
## Syntax  
  
```  
class PrivacyNoticeBindingElement : BindingElement  
{  
  sint32 PrivacyNoticeVersion;  
  string Url;  
};  
```  
  
## Methoden  
 Die PrivacyNoticeBindingElement\-Klasse definiert keine Methoden.  
  
## Eigenschaften  
 Die PrivacyNoticeBindingElement\-Klasse verfügt über die folgenden Eigenschaften:  
  
### PrivacyNoticeVersion  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Version des Datenschutzhinweises  
  
### Url  
 Datentyp: Zeichenfolge  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die URL, an der sich der Datenschutzhinweis befindet.  
  
## Voraussetzungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>