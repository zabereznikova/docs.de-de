---
title: "ServiceMetadataBehavior | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ServiceMetadataBehavior
ServiceMetadataBehavior  
  
## Syntax  
  
```  
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## Methoden  
 Die ServiceMetadataBehavior\-Klasse definiert keine Methoden.  
  
## Eigenschaften  
 Die ServiceMetadataBehavior\-Klasse verfügt über die folgenden Eigenschaften:  
  
### ExternalMetadataLocation  
 Datentyp: Zeichenfolge  
  
 Zugriffstyp: Schreibgeschützt  
  
 Legt den Speicherort fest, zu dem der Dienst Metadatenanforderungen umleitet.  
  
### HttpGetEnabled  
 Datentyp: Boolescher Wert  
  
 Zugriffstyp: Schreibgeschützt  
  
 Steuert, ob der Dienst seine WSDL unter der vom `HttpGetUrl`\-Attribut gesteuerten Adresse veröffentlicht.  
  
### HttpGetUrl  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Legt den Speicherort fest, an dem die Dienst\-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.  
  
### HttpsGetEnabled  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Steuert, ob der Dienst seine WSDL oder HTTPS unter der vom `HttpsGetUrl`\-Attribut gesteuerten Adresse veröffentlicht.  
  
### HttpsGetUrl  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Legt den Speicherort fest, an dem die Dienst\-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.  
  
## Voraussetzungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>