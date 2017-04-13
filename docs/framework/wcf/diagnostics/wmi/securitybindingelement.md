---
title: "SecurityBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# SecurityBindingElement
SecurityBindingElement  
  
## Syntax  
  
```  
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## Methoden  
 Die SecurityBindingElement\-Klasse definiert keine Methoden.  
  
## Eigenschaften  
 Die SecurityBindingElement\-Klasse verfügt über die folgenden Eigenschaften:  
  
### DefaultAlgorithmSuite  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt die Algorithmen an, die mit der Bindung verwendet werden sollen.  
  
### IncludeTimestamp  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob jede Nachricht einen Timestamp enthält.  
  
### KeyEntropyMode  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Entropiequelle zum Erstellen von Schlüsseln.  
  
### LocalServiceSecuritySettings  
 Datentyp: LocalServiceSecuritySettings  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die bindungsspezifischen Sicherheitseigenschaften für den lokalen Dienst.  
  
### MessageSecurityVersion  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die für Nachrichtensicherheit verwendete Version.  
  
### SecurityHeaderLayout  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Reihenfolge der Elemente im Sicherheitsheader für diese Bindung.  
  
## Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>