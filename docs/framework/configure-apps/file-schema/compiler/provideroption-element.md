---
title: "&lt;providerOption&gt;-Element | Microsoft Docs"
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
  - "provideroption"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<providerOption>-Element"
  - "providerOption-Element"
  - "providerOption"
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
caps.latest.revision: 22
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 22
---
# &lt;providerOption&gt;-Element
Gibt die Versionsattribute für Compiler für einen Sprachanbieter an.  
  
## Syntax  
  
```  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`name`|Erforderliches Attribut.<br /><br /> Gibt den Namen der Option an, z. B. "CompilerVersion".|  
|`value`|Erforderliches Attribut.<br /><br /> Gibt den Wert für die Option an, z. B. "v3.5".|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<configuration\>\-Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Das Stammelement in jeder Konfigurationsdatei, die von der Common Language Runtime und den .NET Framework\-Anwendungen verwendet wird.|  
|[\<system.codedom\>\-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Gibt die Konfigurationseinstellungen für Compiler für verfügbare Sprachanbieter an.|  
|[\<compilers\>\-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Container für die Konfigurationselemente für Compiler. Enthält keine oder mehrere `<compiler>`\-Elemente.|  
|[\<compiler\>\-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Gibt die Konfigurationsattribute für Compiler für einen Sprachanbieter an.|  
  
## Hinweise  
 In .NET Framework, Version 3.5, können CodeDOM\-Codeanbieter \(Code Document Object Model\) anbieterspezifische Optionen unterstützen, indem das `<providerOption>`\-Element verwendet wird.  
  
 .NET Framework 3.5 umfasst aktualisierte .NET Framework 2.0\-Assemblys and stellt in der Version 3.5 neu eingeführte Assemblys mit neuen Typen zur Verfügung.  Die Codeanbieter von Microsoft C\# und Visual Basic sind in .NET Framework 2.0\-Assemblys enthalten, wurden jedoch aktualisiert, um Compiler der Version 3.5 zu unterstützen.  Standardmäßig generieren die aktualisierten Codeanbieter Code für Compiler der Version 2.0.  Sie können die Zielcompilerversion mithilfe des `<providerOption>`\-Elements in die Version 3.5 ändern.  Geben Sie dazu für das `name`\-Attribut "CompilerVersion" und für das `value`\-Attribut "v3.5" an.  Sie müssen der Versionsnummer ein klein geschriebenes "v" voranstellen.  
  
 Sie können die Versionsspezifikation als global festlegen, indem Sie das `<providerOption>`\-Element zur Machine.config\-Datei von .NET Framework 2.0 oder zur Web.config\-Datei hinzufügen.  Wenn Sie die standardmäßige Compilerversion in der Machine.config\-Datei auf 3.5 festlegen, können Sie diese wieder für einzelne Anwendungen in 2.0 ändern, indem Sie das `<providerOption>`\-Element in der Konfigurationsdatei der Anwendung verwenden.  
  
 Implementierungen von CodeDOM\-Codeanbietern können benutzerdefinierte Optionen verarbeiten, indem ein Konstruktor bereitgestellt wird, der einen `providerOptions`\-Parameter des Typs <xref:System.Collections.Generic.IDictionary%602> akzeptiert.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Version 3.5 des C\#\-Codeanbieters, der verwendet werden soll, festgelegt wird.  
  
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
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
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