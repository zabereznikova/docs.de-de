---
title: '&lt;Compilerfehler&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 242a4780443026e751d76c7e80dd9a77cbbbddc7
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2018
---
# <a name="ltcompilergt-element"></a>&lt;Compilerfehler&gt; Element
Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.  
  
 \<Konfiguration-Element >  
\<system.codedom Element>  
\<Compilers-Element >  
\<Compilerfehler >-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<compiler  
  language="languageName[;...;...]"  
  extension="fileExtension[;...;...]"  
  type="typeName, assemblyName"  
  warningLevel="number"  
  compilerOptions="option1 option2"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`compilerOptions`|Optionales Attribut.<br /><br /> Gibt zusätzliche compilerspezifisch Argumente für die Kompilierung an. Die Werte für die `compilerOptions` Attribut werden in der Regel in einem Compileroptionen-Thema für den Compiler aufgelistet. In der Visual Studio 2005-Dokumentation können Sie die Optionen für den Compiler suchen, durch die Suche nach "Compileroptionen" im Index.|  
|`extension`|Erforderliches Attribut.<br /><br /> Enthält eine durch Semikolons getrennte Liste der Dateinamenerweiterungen, die von Quelldateien für das Language-Anbieter verwendet. Z. B. "cs".|  
|`language`|Erforderliches Attribut.<br /><br /> Enthält eine durch Semikolons getrennte Liste der Sprachnamen, die von der Language-Anbieter unterstützt. Z. B. "c#; Cs; Csharp".|  
|`type`|Erforderliches Attribut.<br /><br /> Gibt den Typnamen des Sprachanbieters, einschließlich des Namens der Assembly, die die Implementierung eines Anbieters enthält. Der Typname muss die Anforderungen erfüllen [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`warningLevel`|Optionales Attribut.<br /><br /> Gibt die Warnstufe für Standard-Compiler. Bestimmt die Ebene an, an der der Sprachanbieter Kompilierung Warnungen als Fehler behandelt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<"Provideroption" >-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|Gibt die Version Compilerattribute für einen Sprachanbieter an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<configuration> Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|[\<system.codedom> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.|  
|[\<Compiler >-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Container für compilerkonfigurationselemente; enthält 0 (null) oder mehrere `<compiler>` Elemente.|  
  
## <a name="remarks"></a>Hinweise  
 Jede `<compiler>` Element gibt die compilerkonfigurationsattribute für eine bestimmte Sprache-Anbieter. Der Anbieter erweitert die <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> Klasse für eine bestimmte Sprache; die `<compiler>` -Element definiert den Compiler und den Code-Generator-Einstellungen für den Sprachanbieter.  
  
 .NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config). Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen. Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.  
  
 Compilerfehler Elemente in der Anwendungs- oder Webkonfigurationsdatei können ergänzen oder diesen überschreiben die Einstellungen in der Computerkonfigurationsdatei. Wenn mehr als eine Implementierung eines Anbieters für den gleichen Sprachenname oder der gleichen Erweiterung konfiguriert ist, überschreibt die letzten übereinstimmende Konfiguration alle vorherigen konfigurierten Anbieter für diese Sprache oder die Erweiterung an.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Computerkonfigurationsdatei und der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht ein typisches Compilerkonfigurationselement.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<Compiler >-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [Specifying Fully Qualified Type Names (Angeben vollqualifizierter Typnamen)](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 [Compiler-Element für Compiler für Kompilierung ((ASP.NET Settings Schema)](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e(v=vs.100))
