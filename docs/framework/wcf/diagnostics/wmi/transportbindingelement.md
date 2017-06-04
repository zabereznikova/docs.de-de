---
title: "TransportBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# TransportBindingElement
TransportBindingElement  
  
## Syntax  
  
```  
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## Methoden  
 Von der Klasse TransportBindingElement werden keine Methoden definiert.  
  
## Eigenschaften  
 Die Klasse TransportBindingElement verfügt über die folgenden Eigenschaften:  
  
### ManualAddressing  
 Datentyp: Boolescher Wert  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob der Benutzer die Kontrolle über die Nachrichtenadressierung übernehmen möchte.  
  
### MaxBufferPoolSize  
 Datentyp: sint64  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Pufferpoolgröße der Bindung.  
  
### MaxReceivedMessageSize  
 Datentyp: sint64  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Größe einer Nachricht, die von dieser Bindung verarbeitet wird.  
  
### Schema  
 Datentyp: Zeichenfolge  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das URI\-Schema für den Transport.  
  
## Voraussetzungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.TransportBindingElement>