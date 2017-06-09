---
title: "&lt;compilers&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<compilers>-Element"
  - "Compilerkonfigurationselemente, <compilers>-Element"
  - "compilers-Element"
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;compilers&gt;-Element
Container für Compilerkonfigurationselemente; enthält keine oder mehr Elemente [\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).  
  
## Syntax  
  
```  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<compiler\>\-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Gibt die Konfigurationsattribute für Compiler für einen Sprachanbieter an.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<configuration\>\-Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|[\<system.codedom\>\-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Gibt die Konfigurationseinstellungen für Compiler für verfügbare Sprachanbieter an.|  
  
## Hinweise  
 Das [\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)\-Element enthält die Compilerkonfigurationseinstellungen für Sprachanbieter auf einem Computer.  Jedes [\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)\-Element gibt den Compilerkonfigurationsattributen für einen bestimmten Sprachanbieter an.  
  
 In .NET Framework werden die ursprünglichen Einstellungen für Compiler und Sprachanbieter in der Computerkonfigurationsdatei \(machine.config\) definiert.  Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=fullName>\-Implementierung hinzufügen.  Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName>\-Methode für die programmgesteuerte Auflistung der Konfigurationseinstellungen für Sprachanbieter und Compiler auf einem Computer.  
  
## Konfigurationsdatei  
 Dieses Element kann in der Computerkonfigurationsdatei und der Anwendungskonfigurationsdatei verwendet werden.  
  
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
 [Schema für Compiler\- und Sprachanbietereinstellungen](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)   
 [\<compiler\>\-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)