---
title: "OneWayBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# OneWayBindingElement
OneWayBindingElement  
  
## Syntax  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## Methoden  
 Die Klasse OneWayBindingElement definiert keine Methoden.  
  
## Eigenschaften  
 Die Klasse OneWayBindingElement verfügt über die folgenden Eigenschaften:  
  
### ChannelPoolSettings  
 Datentyp: ChannelPoolSettings  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Kanalpool\-Einstellungen.  
  
### MaxAcceptedChannels  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl von akzeptierten Kanälen.  
  
### PacketRoutable  
 Datentyp: Boolescher Wert  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der angibt, ob das Paket geroutet werden kann.  
  
## Voraussetzungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>