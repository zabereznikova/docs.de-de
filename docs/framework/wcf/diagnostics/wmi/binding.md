---
title: "Bindung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Bindung
wmi\-Bindung  
  
## Syntax  
  
```  
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## Methoden  
 Die Bindungsklasse definiert keine Methoden.  
  
## Eigenschaften  
 Die Bindungsklasse verfügt über die folgenden Eigenschaften.  
  
### BindingElements  
 Datentyp: BindingElement\-Array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Auflistung der durch die Bindung implementierten Bindungselemente.  
  
### CloseTimeout  
 Datentyp: datetime \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, das für den Abschluss eines Schließvorgangs bereitgestellt wird.  
  
### Name  
 Datentyp: Zeichenfolge  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name der Bindung.  
  
### Namespace  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der XML\-Namespace der Bindung.  
  
### OpenTimeout  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, das für den Abschluss eines Öffnungsvorgangs bereitgestellt wird.  
  
### ReceiveTimeout  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, das für den Abschluss eines Empfangsvorgangs bereitgestellt wird.  
  
### Schema  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das URI\-Transportschema, das von den Kanal\- und Listener\-Factorys verwendet wird, die von der Bindung erstellt werden.  
  
### SendTimeout  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, das für den Abschluss eines Sendevorgangs bereitgestellt wird.  
  
## Voraussetzungen  
  
|MOF|Deklariert in Servicemodel.mof|  
|---------|------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.Binding>