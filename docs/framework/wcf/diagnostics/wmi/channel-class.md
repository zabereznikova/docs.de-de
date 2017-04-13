---
title: "Kanalklasse | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Kanalklasse
Kanal  
  
## Syntax  
  
```  
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## Methoden  
 Die Kanalklasse definiert keine Methoden.  
  
## Eigenschaften  
 Die Kanalklasse verfügt über die folgenden Eigenschaften.  
  
### LocalAddress  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der lokale Endpunkt für den Kanal.  
  
### ref  
 Datentyp: Endpunkt  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Verweis auf den Endpunkt, mit dem der Kanal verbunden ist.  
  
### RemoteAddress  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die dem Kanal zugeordnete Remoteadresse.  
  
### SessionId  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die aktuelle Sitzungs\-ID \(sofern vorhanden\).  
  
### Typ  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Kanaltyp.  
  
## Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.ChannelBase>