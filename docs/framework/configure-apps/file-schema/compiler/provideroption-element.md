---
title: <providerOption>-Element
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: c8ba5b9a0680f5e5102c13eb5bb0c1904a168c07
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155400"
---
# <a name="provideroption-element"></a>\<ProviderOption> Element
Gibt die Compilerversionsattribute für einen Sprachanbieter an.  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<Compiler>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Compiler->**](compiler-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**

## <a name="syntax"></a>Syntax  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`name`|Erforderliches Attribut.<br /><br /> Gibt den Namen der Option an. z. B. "CompilerVersion".|  
|`value`|Erforderliches Attribut.<br /><br /> Gibt den Wert für die Option an. z. B. "v3.5".|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Konfiguration> Element](../configuration-element.md)|Das Stammelement in jeder Konfigurationsdatei, die von der Common Language Runtime und den .NET Framework-Anwendungen verwendet wird.|  
|[\<system.codedom> Element](system-codedom-element.md)|Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.|  
|[\<Compiler> Element](compilers-element.md)|Container für Compilerkonfigurationselemente; enthält null `<compiler>` oder mehr Elemente.|  
|[\<Compiler> Element](compiler-element.md)|Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.|  
  
## <a name="remarks"></a>Bemerkungen  
 In .NET Framework Version 3.5 können CodeDOM-Codeanbieter (Code Document Object Model) `<providerOption>` anbieterspezifische Optionen mithilfe des Elements unterstützen.  
  
 .NET Framework 3.5 enthält aktualisierte .NET Framework 2.0-Assemblys und stellt neue Assemblys der Version 3.5 bereit, die neue Typen enthalten. Die Microsoft-Codeanbieter für C- und Visual Basic sind in .NET Framework 2.0-Assemblys enthalten, wurden jedoch aktualisiert, um Compiler der Version 3.5 zu unterstützen. Standardmäßig generieren die aktualisierten Codeanbieter Code für Compiler der Version 2.0. Sie können `<providerOption>` das Element verwenden, um die Zielcompilerversion in 3.5 zu ändern. Geben Sie dazu "CompilerVersion" `name` für das Attribut und "v3.5" für das `value` Attribut an. Sie müssen der Versionsnummer mit einem "v" in Kleinbuchstaben vorangehen.  
  
 Sie können die Versionsspezifikation global `<providerOption>` machen, indem Sie das Element zur Datei .NET Framework 2.0 Machine.config oder root Web.config hinzufügen. Wenn Sie die Standardcompilerversion in der Datei Machine.config auf 3.5 aktualisieren, können Sie sie pro `<providerOption>` Anwendung auf 2.0 zurücksetzen, indem Sie das Element in der Anwendungskonfigurationsdatei verwenden.  
  
 CodeDOM-Codeanbieterimplementierer können benutzerdefinierte Optionen verarbeiten, indem `providerOptions` sie <xref:System.Collections.Generic.IDictionary%602>einen Konstruktor bereitstellen, der einen Parameter vom Typ annimmt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie angeben, dass Version 3.5 des Codeanbieters verwendet werden soll.  
  
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
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Schema der Konfigurationsdatei](../index.md)
- [\<Compiler> Element](compilers-element.md)
- [Angeben vollständig gekennzeichneter Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [compiler-Element für compilers für compilation (ASP.NET-Einstellungsschema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
