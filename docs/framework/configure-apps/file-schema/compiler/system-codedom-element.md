---
title: <system.codedom>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 40a3c84e1deed4d215383670176623a6a79ac41d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155387"
---
# <a name="systemcodedom-element"></a>\<system.codedom>-Element
Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.codedom>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<compilers>](compilers-element.md)|Container für Compilerkonfigurationselemente; enthält 0 (null) oder mehr- [\<compiler>](compiler-element.md) Elemente.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="net-framework-version-20"></a>.NET Framework Version 2,0  
 Das [\<system.codedom>](system-codedom-element.md) -Element enthält die Compilerkonfigurationseinstellungen für Sprachanbieter, die auf einem Computer installiert sind, zusätzlich zu den Standard Anbietern, die mit dem .NET Framework installiert werden, z <xref:Microsoft.CSharp.CSharpCodeProvider> <xref:Microsoft.VisualBasic.VBCodeProvider> . b. und. Das- [\<compilers>](compilers-element.md) Element enthält NULL oder mehr- [\<compiler>](compiler-element.md) Elemente. Jedes- [\<compiler>](compiler-element.md) Element gibt die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an.  
  
 Entwickler und Compileranbieter können der Computer Konfigurationsdatei (Machine. config) für eine neue Implementierung Konfigurationseinstellungen hinzufügen <xref:System.CodeDom.Compiler.CodeDomProvider> . Verwenden <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> Sie die-Methode, um die Standard Sprachanbieter und Sprachanbieter, die von den Compilerkonfigurationseinstellungen eines Computers identifiziert werden, Programm gesteuert aufzuzählen.  
  
> [!NOTE]
> In den .NET Framework Versionen 1,0 und 1,1 werden die von der .NET Framework bereitgestellten Standard Sprachanbieter im- [\<compilers>](compilers-element.md) Element identifiziert. In der .NET Framework Version 2,0 werden die Standard Sprachanbieter nicht im-Element identifiziert [\<compilers>](compilers-element.md) , Sie können jedoch mit der-Methode aufgelistet werden <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> .  
  
## <a name="net-framework-versions-10-and-11"></a>.NET Framework Versionen 1,0 und 1,1  
 Das- [\<system.codedom>](system-codedom-element.md) Element enthält die Compilerkonfigurationseinstellungen für Sprachanbieter auf einem Computer. Das- [\<compilers>](compilers-element.md) Element enthält NULL oder mehr- [\<compiler>](compiler-element.md) Elemente. Jedes- [\<compiler>](compiler-element.md) Element gibt die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an.  
  
 .NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config). Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen. Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Computer Konfigurationsdatei und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht eine typische Compilerkonfiguration.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Konfigurationsdateischema](../index.md)
- [Schema für Compiler- und Sprachanbietereinstellungen](index.md)
- [\<compiler>Gewisses](compiler-element.md)
