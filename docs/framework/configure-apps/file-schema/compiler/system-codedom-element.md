---
title: "&lt;system.codedom&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<system.codedom>-Element"
  - "Compilerkonfigurationselemente, <system.codedom>-Element"
  - "system.codedom-Element"
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# &lt;system.codedom&gt;-Element
Gibt die Konfigurationseinstellungen für Compiler für verfügbare Sprachanbieter an.  
  
## Syntax  
  
```  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Container für Compilerkonfigurationselemente; enthält keine oder mehr Elemente [\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<konfiguration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
  
## Hinweise  
  
## .NET Framework\-Version 2.0  
 Das [\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)\-Element enthält Compilerkonfigurationseinstellungen für die Sprachanbieter, die auf einem Computer \(zusätzlich zu den Standardanbietern installiert werden, die mit .NET Framework, wie <xref:Microsoft.CSharp.CSharpCodeProvider> und <xref:Microsoft.VisualBasic.VBCodeProvider> einrichten.  Das [\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)\-Element enthält keine oder mehr Elemente [\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).  Jedes [\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)\-Element gibt den Compilerkonfigurationsattributen für einen bestimmten Sprachanbieter an.  
  
 Entwickler und Compileranbieter können in die Konfigurationsdatei des Computers \(Machine.config\) Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>\-Implementierung einfügen.  Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName>\-Methode für die programmgesteuerte Auflistung der Standardsprachanbieter und der Sprachanbieter, die über die Konfigurationseinstellungen für Compiler auf einem Computer angegeben sind.  
  
> [!NOTE]
>  In den .NET Framework\-Versionen 1.0 und 1,1, werden die Standardspracheanbieter, die von .NET Framework bereitgestellten, im [\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)\-Element identifiziert.  In .NET Framework Version 2.0, werden die Standardspracheanbieter nicht im [\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)\-Element identifiziert, sondern können mit der <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A>\-Methode aufgelistet werden.  
  
## .NET Framework Version 1.0 und 1.1  
 Das [\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)\-Element enthält die Compilerkonfigurationseinstellungen für Sprachanbieter auf einem Computer.  Das [\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)\-Element enthält keine oder mehr Elemente [\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).  Jedes [\<Compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)\-Element gibt den Compilerkonfigurationsattributen für einen bestimmten Sprachanbieter an.  
  
 In .NET Framework werden die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei \(machine.config\) definiert.  Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>\-Implementierung hinzufügen.  Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName>\-Methode für die programmgesteuerte Auflistung der Konfigurationseinstellungen für Sprachanbieter und Compiler auf einem Computer.  
  
## Konfigurationsdatei  
 Dieses Element kann in der Computerkonfigurationsdatei und der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel ist eine typische Compilerkonfiguration dargestellt.  
  
```  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler   
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=1.0.5000.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
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