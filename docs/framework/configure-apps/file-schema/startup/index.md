---
title: "Schema f&#252;r Starteinstellungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Konfigurationsschema [.NET Framework], Starteinstellungen"
  - "Schema für Starteinstellungen"
  - "Starteinstellungsschema"
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Schema f&#252;r Starteinstellungen
Starteinstellungen geben die Version der Common Language Runtime an, mit der die Anwendung ausgeführt werden soll.  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<requiredRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|Gibt an, dass die Anwendung lediglich Version 1.0 der Common Language Runtime unterstützt.  Anwendungen, die mit der Laufzeitversion 1.1 erstellt werden, sollten die **\<supportedRuntime\>**\-Element verwenden.|  
|[\<supportedRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.|  
|[\<startup\>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|Enthält die **\<requiredRuntime\>** und **\<supportedRuntime\>**\-Elemente.|  
  
## Siehe auch  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Specifying Which Runtime Version to Use](http://msdn.microsoft.com/de-de/c376208d-980d-42b4-865b-fbe0d9cc97c2)