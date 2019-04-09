---
title: <providerOption> Element
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: 9c69ea7bf95b311a796ec29d90410a77b748c3c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229783"
---
# <a name="provideroption-element"></a>\<"Provideroption" >-Element
Gibt die Compiler-Version-Attribute für einen Sprachanbieter an.  
  
 \<Configuration-Element >  
\<System.CodeDom-Element >  
\<Compilers-Element >  
\<Compilerfehler >-Element  
\<"Provideroption" >-Element  
  
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
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`name`|Erforderliches Attribut.<br /><br /> Gibt den Namen der Option. Beispiel: "CompilerVersion".|  
|`value`|Erforderliches Attribut.<br /><br /> Gibt den Wert für die Option an. z. B. "v3. 5".|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Configuration >-Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Das Stammelement in jeder Konfigurationsdatei, die von der Common Language Runtime und den .NET Framework-Anwendungen verwendet wird.|  
|[\<System.CodeDom >-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.|  
|[\<Compiler > Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Container für compilerkonfigurationselemente; enthält 0 (null) oder mehr `<compiler>` Elemente.|  
|[\<Compilerfehler >-Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.|  
  
## <a name="remarks"></a>Hinweise  
 In .NET Framework, Version 3.5, können Code Document Object Model (CodeDOM)-Codeanbieter anbieterspezifische Optionen unterstützen, mithilfe der `<providerOption>` Element.  
  
 .NET Framework 3.5 enthält aktualisierte .NET Framework 2.0-Assemblys sowie neue Assemblys der Version 3.5, die neue Typen enthalten. Die Microsoft C#- und Visual Basic-Code-Anbieter sind in .NET Framework 2.0-Assemblys enthalten, aber es wurden aktualisiert, um die Version 3.5-Compiler unterstützen. Standardmäßig generiert die aktualisierten Codeanbieter Code für Version 2.0-Compiler. Sie können die `<providerOption>` Element in der Ziel-Compilerversion 3.5 ändern. Zu diesem Zweck geben Sie "CompilerVersion" für die `name` -Attribut und "v3. 5" für die `value` Attribut. Sie müssen die Versionsnummer mit einem Kleinbuchstaben "V" voranstellen.  
  
 Sie können die Spezifikation der Version von der globalen vornehmen, durch das Hinzufügen der `<providerOption>` Elements, das die .NET Framework 2.0 "Machine.config" oder die Stammdatei "Web.config". Wenn Sie die Standard-Compiler-Version 3.5 in der Datei Machine.config aktualisieren, können Sie es wieder in 2.0 auf einer Basis pro Anwendung ändern, mit der `<providerOption>` Element in der Konfigurationsdatei der Anwendung.  
  
 CodeDOM-Code implementieren, können benutzerdefinierte Optionen verarbeiten, indem Sie einen Konstruktor bereitstellen, akzeptiert eine `providerOptions` Parameter vom Typ <xref:System.Collections.Generic.IDictionary%602>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das angeben, dass die Version 3.5 des C#-Code-Anbieters verwendet werden soll.  
  
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
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<Compiler > Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)
- [Angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [compiler-Element für compilers für compilation (ASP.NET-Einstellungsschema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
