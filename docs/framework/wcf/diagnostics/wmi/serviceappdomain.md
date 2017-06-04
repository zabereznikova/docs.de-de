---
title: "ServiceAppDomain | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ServiceAppDomain
Ordnet einer Anwendungsdomäne einen Dienst zu.  
  
## Syntax  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## Methoden  
 Mit der ServiceAppDomain\-Klasse werden keine Methoden definiert.  
  
## Eigenschaften  
 Die ServiceAppDomain\-Klasse verfügt über die folgenden Eigenschaften:  
  
### ref  
 Datentyp: Dienst               
 Qualifizierer: Schlüssel  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Dienst dieser Anwendungsdomäne.  
  
### ref  
 Datentyp: AppDomainInfo               
 Qualifizierer: Schlüssel  
  
 Zugriffstyp: Schreibgeschützt  
  
 Enthält Eigenschaften der Anwendungsdomäne.  
  
## Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|