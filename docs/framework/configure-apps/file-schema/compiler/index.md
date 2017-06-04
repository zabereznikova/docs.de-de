---
title: "Schema f&#252;r Compiler- und Sprachanbietereinstellungen | Microsoft Docs"
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
  - "Compilerkonfigurationselemente"
  - "Compilerkonfigurationselemente, Schema"
  - "Compilerkonfigurationseinstellungen"
  - "Compilerkonfigurationseinstellungen, Schema"
  - "Konfigurationsschema [.NET Framework], Compilereinstellungen"
  - "Konfigurationseinstellungen [.NET Framework], Compiler"
  - "Sprachenanbieter"
  - "Sprachenanbieter, Einstellungsschema"
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Schema f&#252;r Compiler- und Sprachanbietereinstellungen
Mithilfe von Compiler\- und Sprachanbietereinstellungen werden Konfigurationselemente für Compiler für verfügbare Sprachanbieter festgelegt.  Jedes Konfigurationselement für Compiler gibt den Typnamen des Codeanbieters, die Compilerparameter sowie die unterstützten Sprachenamen und Dateierweiterungen an.  
  
 In .NET Framework werden die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei \(machine.config\) definiert.  Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>\-Implementierung hinzufügen.  Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName>\-Methode für die programmgesteuerte Auflistung der Konfigurationseinstellungen für Sprachanbieter und Compiler auf einem Computer.  
  
 [\<configuration\>\-Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)  
  
 [\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
  
 [\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Gibt die Konfigurationseinstellungen für Compiler für verfügbare Sprachanbieter an.|  
|[\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Container für Compilerkonfigurationselemente; enthält keine oder mehr Elemente [\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).|  
|[\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Gibt die Konfigurationsattribute für Compiler für einen Sprachanbieter an.|  
  
## Beispiel  
 Im folgenden Beispiel wird ein typisches Konfigurationselement für Compiler dargestellt.  
  
```  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler  
          language="c#;cs;csharp"  
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""  
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.CodeDom.Compiler.CompilerInfo>   
 <xref:System.CodeDom.Compiler.CodeDomProvider>   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<compiler\>\-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)