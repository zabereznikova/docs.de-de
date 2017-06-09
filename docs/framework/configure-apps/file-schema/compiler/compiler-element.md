---
title: "&lt;compiler&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<compiler>-Element"
  - "Compilerkonfigurationsattribute"
  - "Compilerkonfigurationselemente, <compiler>-Element"
  - "compiler-Element"
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# &lt;compiler&gt;-Element
Gibt die Konfigurationsattribute für Compiler für einen Sprachanbieter an.  
  
## Syntax  
  
```  
<compiler  
  language="languageName[;...;...]"  
  extension="fileExtension[;...;...]"  
  type="typeName, assemblyName"  
  warningLevel="number"  
  compilerOptions="option1 option2"  
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`compilerOptions`|Optionales Attribut.<br /><br /> Gibt zusätzliche compilerspezifische Argumente für die Kompilierung an.  Die Werte für das `compilerOptions`\-Attribut werden normalerweise in einem Compileroptionen\-Thema für den Compiler aufgelistet.  Sie finden die Optionen für den Compiler in der Dokumentation zu Visual Studio 2005, indem Sie im Index nach "Compileroptionen" suchen.|  
|`extension`|Erforderliches Attribut.<br /><br /> Gibt eine durch Semikolons getrennte Liste der für Quelldateien des Sprachanbieters verwendeten Datenamenerweiterungen an.  Beispiel: ".cs".|  
|`language`|Erforderliches Attribut.<br /><br /> Gibt eine durch Semikolons getrennte Liste mit vom Sprachanbieter unterstützten Sprachnamen an.  Beispiel: "c\#;cs;csharp".|  
|`type`|Erforderliches Attribut.<br /><br /> Gibt den Typnamen des Sprachanbieters und den Namen der Assembly an, die die Anbieterimplementierung enthält.  Der Typname muss den unter [Angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md) definierten Anforderungen entsprechen.|  
|`warningLevel`|Optionales Attribut.<br /><br /> Gibt die standardmäßige Compilerwarnungsebene an. Bestimmt die Ebene, ab der der Sprachanbieter Compilerwarnungen als Fehler behandelt.|  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<providerOption\>\-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|Gibt Versionsattribute für Compiler für einen Sprachanbieter an.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<configuration\>\-Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|[\<system.codedom\>\-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Gibt die Konfigurationseinstellungen für Compiler für verfügbare Sprachanbieter an.|  
|[\<compilers\>\-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Container für die Konfigurationselemente für Compiler. Enthält keine oder mehrere `<compiler>`\-Elemente.|  
  
## Hinweise  
 Jedes `<compiler>`\-Element gibt Konfigurationsattribute für Compiler für einen bestimmten Sprachanbieter an.  Der Anbieter erweitert die <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=fullName>\-Klasse für eine bestimmte Sprache; das `<compiler>`\-Element definiert die Einstellungen für Compiler und Codegenerator für den Sprachanbieter.  
  
 In .NET Framework werden die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei \(machine.config\) definiert.  Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>\-Implementierung hinzufügen.  Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName>\-Methode für die programmgesteuerte Auflistung der Konfigurationseinstellungen für Sprachanbieter und Compiler auf einem Computer.  
  
 Compilerelemente in der Anwendungs\- oder Webkonfigurationsdatei können die Einstellungen in der Computerkonfigurationsdatei ergänzen oder überschreiben.  Bei der Konfiguration mehrerer Anbieterimplementierungen für denselben Sprachnamen oder dieselbe Dateierweiterung überschreibt die letzte übereinstimmende Konfiguration alle vorherigen konfigurierten Anbieter für den Sprachnamen oder die Dateierweiterung.  
  
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
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.CodeDom.Compiler.CompilerInfo>   
 <xref:System.CodeDom.Compiler.CodeDomProvider>   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<compilers\>\-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)   
 [Angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)   
 [compiler\-Element für compilers für compilation \(ASP.NET\-Einstellungsschema\)](http://msdn.microsoft.com/de-de/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)