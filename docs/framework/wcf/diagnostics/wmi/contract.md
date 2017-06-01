---
title: "Vertrag | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Vertrag
Contract  
  
## Syntax  
  
```  
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## Methoden  
 Die Contract\-Klasse definiert keine Methoden.  
  
## Eigenschaften  
 Die Contract\-Klasse verfügt über die folgenden Eigenschaften:  
  
### AppDomainId  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Anwendungsdomänen\-ID der Anwendungsdomäne, die den Vertrag hostet.  
  
### Behaviors  
 Datentyp: Behavior\-Array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die mit diesem Vertrag verknüpften Verhalten.  
  
### Name  
 Datentyp: Zeichenfolge  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name des Vertrags in WSDL.  
  
### Namespace  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Namespace des `portType`\-Elements in WSDL.  
  
### Operations  
 Datentyp: Operation\-Array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Vorgang dieses Vertrags.  
  
### ProcessId  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Porzess\-ID des Prozesses, der den Vertrag hostet.  
  
### ref  
 Datentyp: Contract  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Typ des Rückrufs, wenn es sich beim Vertrag um einen Duplexvertrag handelt.  
  
### SessionMode  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob der Vertrag die ihm zugeordnete Bindung für die Verwendung der Kanalsitzung benötigt.  
  
### Type  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Typ des Vertrags.  
  
## Voraussetzungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Description.ContractDescription>