---
title: "XmlDictionaryReaderQuotas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# XmlDictionaryReaderQuotas
XmlDictionaryReaderQuotas  
  
## Syntax  
  
```  
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## Methoden  
 Von der XmlDictionaryReaderQuotas\-Klasse werden keine Methoden definiert.  
  
## Eigenschaften  
 Die XmlDictionaryReaderQuotas\-Klasse weist die folgenden Eigenschaften auf:  
  
### MaxArrayLength  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximal zulässige Arraylänge.  
  
### MaxBytesPerRead  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximal zulässigen Bytes, die bei jedem Lesevorgang zurückgegeben werden.  
  
### MaxDepth  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale geschachtelte Knotentiefe für jeden Lesevorgang.  
  
### MaxNameTableCharCount  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximal zulässigen Zeichen in einem Tabellennamen.  
  
### MaxStringContentLength  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Zeichenanzahl, die in XML\-Elementinhalten zulässig ist.  
  
## Voraussetzungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.Xml.XmlDictionaryReaderQuotas>   
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>