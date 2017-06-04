---
title: "Operation-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Operation-Klasse
Operation  
  
## Syntax  
  
```  
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## Methoden  
 Die Operation\-Klasse definiert keine Methoden.  
  
## Eigenschaften  
 Die Operation\-Klasse verfügt über die folgenden Eigenschaften:  
  
### Action  
 Datentyp: Zeichenfolge  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die WS\-Adressierungsaktion der Anforderungsnachricht.  
  
### AsyncPattern  
 Datentyp: Boolescher Wert  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, dass ein Vorgang asynchron implementiert wird, indem in einem Dienstvertrag das Methodenpaar `Begin` \[spitze Klammern öffnen\/schließen\] und `End` \[spitze Klammern öffnen\/schließen\] verwendet wird.  
  
### Behaviors  
 Datentyp: Array für Verhalten  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die mit diesem Vorgang verknüpften Verhalten.  
  
### IsCallback  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 True, wenn der Vorgang ein Rückrufvorgang ist.  
  
### IsInitiating  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob die Methode einen Vorgang implementiert, der eine Sitzung auf dem Server initiieren kann.  
  
### IsOneWay  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob ein Vorgang eine Antwortnachricht zurückgibt.  
  
### IsTerminating  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob ein Vorgang eine Antwortnachricht zurückgibt.  
  
### MethodSignature  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Methodensignatur des Vorgangs.  
  
### Name  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name des Vorgangs.  
  
### ParameterTypes  
 Datentyp: Zeichenfolgenarray  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Parametertypen des Vorgangs.  
  
### ReplyAction  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Wert der SOAP\-Aktion für die Antwortnachricht des Vorgangs.  
  
### ReturnType  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Rückgabetyp des Vorgangs.  
  
## Voraussetzungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Description.OperationDescription>