---
title: <compiler>-Element
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
ms.openlocfilehash: 46676f25597f85596598d6f67c98930971cb0447
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088056"
---
# <a name="compiler-element"></a>\<Compiler > Element

Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. CodeDom->** ](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Compiler**](compilers-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<- **Compiler>**

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
|`compilerOptions`|Optionales Attribut.<br /><br /> Gibt zusätzliche compilerspezifische Argumente für die Kompilierung an. Die Werte für das `compilerOptions`-Attribut werden in der Regel in einem Compileroptionen-Thema für den Compiler aufgeführt.|
|`extension`|Erforderliches Attribut.<br /><br /> Stellt eine durch Semikolons getrennte Liste der Dateinamen Erweiterungen bereit, die von den Quelldateien für den Sprachanbieter verwendet werden. Beispiel: ". cs".|
|`language`|Erforderliches Attribut.<br /><br /> Stellt eine durch Semikolons getrennte Liste der vom Sprachanbieter unterstützten Sprachnamen bereit. Beispiel: "c#; cs; csharp".|
|`type`|Erforderliches Attribut.<br /><br /> Gibt den Typnamen des sprach Anbieters an, einschließlich des Namens der Assembly, die die Anbieter Implementierung enthält. Der Typname muss die in [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)definierten Anforderungen erfüllen.|
|`warningLevel`|Optionales Attribut.<br /><br /> Gibt die Standard-compilerwartebene an. bestimmt die Ebene, auf der der Sprachanbieter Kompilierungs Warnungen als Fehler behandelt.|

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<Provideroption-> Element](provideroption-element.md)|Gibt Attribute der Compilerversion für einen Sprachanbieter an.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<configuration> Element](../configuration-element.md)|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|[\<System. CodeDom >-Element](system-codedom-element.md)|Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.|
|[\<Compiler > Element](compilers-element.md)|Container für Compilerkonfigurationselemente; enthält 0 (null) oder mehr `<compiler>` Elemente.|

## <a name="remarks"></a>Hinweise

Jedes `<compiler>`-Element gibt die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an. Der Anbieter erweitert die <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> Klasse für eine bestimmte Sprache. Das `<compiler>`-Element definiert die Compiler-und Code-Generator-Einstellungen für den Sprachanbieter.

.NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config). Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen. Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.

Compilerelemente in der Anwendungs-oder Webkonfigurationsdatei können die Einstellungen in der Computer Konfigurationsdatei ergänzen oder überschreiben. Wenn mehr als eine Anbieter Implementierung für denselben Sprachnamen oder dieselbe Dateierweiterung konfiguriert ist, überschreibt die letzte übereinstimmende Konfiguration alle zuvor konfigurierten Anbieter für diesen Sprachnamen oder die Dateierweiterung.

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Computer Konfigurationsdatei und in der Anwendungs Konfigurationsdatei verwendet werden.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht ein typisches compilerkonfigurationselement:

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
- [Konfigurationsdateischema](../index.md)
- [\<Compiler > Element](compilers-element.md)
- [Specifying Fully Qualified Type Names (Angeben vollqualifizierter Typnamen)](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [Compiler-Element für Compiler für die Kompilierung (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
