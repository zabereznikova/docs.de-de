---
title: '&lt;Compilerfehler&gt; Element'
ms.date: 08/14/2018
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 84000d8762c5d5cfd8d2359a377ffcd5b50ab07c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502849"
---
# <a name="ltcompilergt-element"></a>&lt;Compilerfehler&gt; Element

Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.

\<Configuration-Element > \<system.codedom-Element > \<Compilers-Element > \<Compiler > Element

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
|`compilerOptions`|Optionales Attribut.<br /><br /> Gibt zusätzliche compilerspezifische Argumente für die Kompilierung an. Die Werte für die `compilerOptions` Attribut finden Sie in der Regel in einem Compileroptionen-Thema für den Compiler.|
|`extension`|Erforderliches Attribut.<br /><br /> Enthält eine durch Semikolons getrennte Liste der Dateinamenerweiterungen, die von Quelldateien verwendet werden, für den Sprachanbieter an. Z. B. ". cs".|
|`language`|Erforderliches Attribut.<br /><br /> Enthält eine durch Semikolons getrennte Liste von vom Sprachanbieter unterstützten Sprachnamen. Z. B. "c#; Cs; Csharp".|
|`type`|Erforderliches Attribut.<br /><br /> Gibt den Typnamen des Sprachanbieters, einschließlich des Namens der Assembly, die die anbieterimplementierung enthält. Der Typname muss die Anforderungen erfüllen [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|
|`warningLevel`|Optionales Attribut.<br /><br /> Gibt die Warnstufe des Compilers "Standard" an. Bestimmt die Ebene, die mit der des Sprachanbieters für compilerwarnungen als Fehler behandelt.|

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<"Provideroption" >-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|Gibt den Compilerfehler Version-Attribute für einen Sprachanbieter an.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<configuration> Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|[\<System.CodeDom >-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.|
|[\<Compiler > Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Container für compilerkonfigurationselemente; enthält 0 (null) oder mehr `<compiler>` Elemente.|

## <a name="remarks"></a>Hinweise

Jede `<compiler>` Element gibt die compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an. Der Datenanbieter erweitert die <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> -Klasse für eine bestimmte Sprache; der `<compiler>` -Element definiert den Compiler und den Code-Generator-Einstellungen für den Sprachanbieter.

.NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config). Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen. Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.

Compilerfehler Elemente der Anwendungs-oder Webkonfigurationsdatei können ergänzen oder überschreiben die Einstellungen in der Computerkonfigurationsdatei. Wenn mehr als eine Implementierung eines Anbieters für den Namen der gleichen Sprache oder die gleiche Dateierweiterung konfiguriert ist, überschreibt die letzten übereinstimmende Konfiguration alle vorherigen konfigurierten Anbieter für diese Sprache oder die Erweiterung an.

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Konfigurationsdatei des Computers und der Anwendungskonfigurationsdatei verwendet werden.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht ein typisches Compilerkonfigurationselement:

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

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<Compiler > Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)
- [Angeben vollqualifizierter vollqualifizierte Typnamen]-(.. /.. /.. /.. /.. / docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [Compiler-Element für Compilers für Compilation ((ASP.NET Einstellungsschema)](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e(v=vs.100))
