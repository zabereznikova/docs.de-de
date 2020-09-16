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
ms.openlocfilehash: 7e006adb86886d22ec08dc61fa092bf677b4da96
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544738"
---
# <a name="provideroption-element"></a>\<providerOption>-Element
Gibt die compilerversions-Attribute für einen Sprachanbieter an.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)\
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
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`name`|Erforderliches Attribut.<br /><br /> Gibt den Namen der Option an. Beispiel: "Compilerversion".|  
|`value`|Erforderliches Attribut.<br /><br /> Gibt den Wert für die Option an. Beispiel: "v 3.5".|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<configuration>-Element](../configuration-element.md)|Das Stammelement in jeder Konfigurationsdatei, die von der Common Language Runtime und den .NET Framework-Anwendungen verwendet wird.|  
|[\<system.codedom>-Element](system-codedom-element.md)|Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.|  
|[\<compilers>-Element](compilers-element.md)|Container für Compilerkonfigurationselemente; enthält 0 (null) oder mehr- `<compiler>` Elemente.|  
|[\<compiler>-Element](compiler-element.md)|Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.|  
  
## <a name="remarks"></a>Hinweise  
 In der .NET Framework Version 3,5 können Code Document Object Model (CodeDom)-Code Anbieter anbieterspezifische Optionen mithilfe des-Elements unterstützen `<providerOption>` .  
  
 Der .NET Framework 3,5 umfasst aktualisierte .NET Framework 2,0-Assemblys und stellt neue Version 3,5-Assemblys bereit, die neue Typen enthalten. Die Microsoft c#-und Visual Basic-Code Anbieter sind in .NET Framework 2,0-Assemblys enthalten, wurden jedoch aktualisiert, um Compiler der Version 3,5 zu unterstützen. Standardmäßig generieren die aktualisierten Code Anbieter Code für Compiler der Version 2,0. Sie können das- `<providerOption>` Element verwenden, um die Ziel-Compilerversion in 3,5 zu ändern. Geben Sie hierzu "Compilerversion" für das `name` -Attribut und "v 3.5" für das- `value` Attribut an. Sie müssen der Versionsnummer einen Kleinbuchstaben "v" voranstellen.  
  
 Sie können die Versions Spezifikation Global machen, indem Sie das- `<providerOption>` Element der Datei .NET Framework 2,0 Machine.config oder Root Web.config hinzufügen. Wenn Sie die Standard-Compilerversion in der Machine.config-Datei auf 3,5 aktualisieren, können Sie Sie auf Anwendungs Basis wieder in 2,0 ändern, indem Sie das- `<providerOption>` Element in der Anwendungs Konfigurationsdatei verwenden.  
  
 CodeDOM-Code Anbieter Implementierer können benutzerdefinierte Optionen verarbeiten, indem Sie einen Konstruktor bereitstellen, `providerOptions` der einen Parameter vom Typ annimmt <xref:System.Collections.Generic.IDictionary%602> .  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie angegeben wird, dass Version 3,5 des c#-Code Anbieters verwendet werden soll.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Konfigurationsdateischema](../index.md)
- [\<compilers>-Element](compilers-element.md)
- [Specifying Fully Qualified Type Names (Angeben vollqualifizierter Typnamen)](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [compiler-Element für compilers für compilation (ASP.NET-Einstellungsschema)](/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
