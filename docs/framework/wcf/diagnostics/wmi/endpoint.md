---
title: "Endpunkt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Endpunkt
Endpunkt  
  
## Syntax  
  
```  
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## Methoden  
 Von der Endpoint\-Klasse wird die folgende Methode definiert:  
  
|Methode|Beschreibung|  
|-------------|------------------|  
|[GetOperationCounterInstanceName](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|Ruft den Instanznamen des Vorgangsleistungsindikators ab.|  
  
## Eigenschaften  
 Die Endpoint\-Klasse verfügt über die folgenden Eigenschaften:  
  
### Adresse  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein URI, der die Adresse des Endpunkts enthält.  
  
### AddressHeaders  
 Datentyp: Zeichenfolgenarray  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Auflistung von Adressheadern, die diesem Endpunkt angefügt sind.  
  
### AddressIdentity  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Identität des Endpunkts.  
  
### AppDomainId  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Anwendungsdomänen\-ID der Anwendungsdomäne, von der der Endpunkt gehostet wird.  
  
### Verhalten  
 Datentyp: Behavior\-Array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Auflistung der von diesem Endpunkt implementierten Verhaltensweisen.  
  
### Bindung  
 Datentyp: Bindung  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die von diesem Endpunkt verwendete Bindung.  
  
### ContractName  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden.  
  
### CounterInstanceName  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Instanzname der Leistungsindikatoren des Endpunkts.  
  
### ListenUri  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der URI, der vom Endpunkt zum Abhören verwendet wird.  
  
### Name  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der eindeutige Name des Endpunkts.  
  
### ProcessId  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Prozess\-ID des Prozesses, von dem der Endpunkt gehostet wird.  
  
### ref  
 Datentyp: Contract  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Vertrag, der von diesem Endpunkt verfügbar gemacht wird.  
  
## Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|