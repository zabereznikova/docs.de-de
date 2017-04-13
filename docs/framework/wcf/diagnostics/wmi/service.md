---
title: "Dienst | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Dienst
Dienst  
  
## Syntax  
  
```  
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## Methoden  
 Die Dienstklasse definiert keine Methoden.  
  
## Eigenschaften  
 Die Dienstklasse hat die folgenden Eigenschaften:  
  
### BaseAddresses  
 Datentyp: Zeichenfolgenarray  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die vom Dienst verwendeten Basisadressen.  
  
### Behaviors  
 Datentyp: Behavior\-Array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die diesem Dienst zugewiesenen Verhalten.  
  
### ConfigurationName  
 Datentyp: Zeichenfolge  
  
 Zugriffstyp: Schreibgeschützt  
  
 ServiceElement\_BehaviorConfiguration  
  
### CounterInstanceName  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Name der Instanz der Leistungsindikatoren des Dienstes.  
  
### DistinguishedName  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Dienstname an der Adresse.  
  
### Extensions  
 Datentyp: Zeichenfolgenarray  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Instanzkontexte für die Erweiterungen der Dienstinstanz.  
  
### Metadata  
 Datentyp: Zeichenfolgenarray  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Dienstmetadateneinstellungen.  
  
### Name  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der eindeutige Name des Dienstes.  
  
### Namespace  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Namespace des Dienstes.  
  
### Opened  
 Datentyp: datetime \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Zeit, zu der der Dienst geöffnet wurde.  
  
### OutgoingChannels  
 Data type: Channel array \(Kanal\-Array\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Kanäle, die von der Dienstinstanz ausgehen.  
  
### ProcessId  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Prozess\-ID des Vorgangs, von dem der Dienst gehostet wird.  
  
## Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|