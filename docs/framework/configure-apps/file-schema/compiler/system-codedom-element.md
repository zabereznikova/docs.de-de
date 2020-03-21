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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155387"
---
# <a name="systemcodedom-element"></a>\<system.codedom> Element
Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.  
  
[**\<Konfiguration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.codedom>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Compiler>](compilers-element.md)|Container für Compilerkonfigurationselemente; enthält null oder mehr [ \<Compiler>](compiler-element.md) Elemente enthält.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Konfiguration>](../configuration-element.md)|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="net-framework-version-20"></a>.NET Framework Version 2.0  
 Das [ \<system.codedom>-Element](system-codedom-element.md) enthält Compilerkonfigurationseinstellungen für Sprachanbieter, die auf einem Computer installiert sind, zusätzlich <xref:Microsoft.CSharp.CSharpCodeProvider> zu <xref:Microsoft.VisualBasic.VBCodeProvider>den Standardanbietern, die mit .NET Framework installiert sind, z. B. die und die . Die [ \<Compiler>](compilers-element.md) Element enthält null oder mehr [ \<Compiler>](compiler-element.md) Elemente. Jeder [ \<Compiler>-Element](compiler-element.md) die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter angibt.  
  
 Entwickler und Compilerhersteller können der Computerkonfigurationsdatei (Machine.config) Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider> Implementierung hinzufügen. Verwenden <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> Sie die Methode, um sowohl die Standardsprachanbieter als auch die Sprachanbieter, die durch die Compilerkonfigurationseinstellungen auf einem Computer identifiziert werden, programmgesteuert aufzuzählen.  
  
> [!NOTE]
> In den .NET Framework-Versionen 1.0 und 1.1 werden die von .NET Framework bereitgestellten Standardsprachenanbieter in den [ \<Compilern>-Element](compilers-element.md) identifiziert. In .NET Framework Version 2.0 werden die Standardsprachanbieter nicht in den <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> [ \<Compilern identifiziert>-Element,](compilers-element.md) sondern können mit der Methode aufgezählt werden.  
  
## <a name="net-framework-versions-10-and-11"></a>.NET Framework-Versionen 1.0 und 1.1  
 Das [ \<system.codedom>-Element](system-codedom-element.md) enthält die Compilerkonfigurationseinstellungen für Sprachanbieter auf einem Computer. Die [ \<Compiler>](compilers-element.md) Element enthält null oder mehr [ \<Compiler>](compiler-element.md) Elemente. Jeder [ \<Compiler>-Element](compiler-element.md) die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter angibt.  
  
 .NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config). Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen. Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Maschinenkonfigurationsdatei und in der Anwendungskonfigurationsdatei verwendet werden.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Schema der Konfigurationsdatei](../index.md)
- [Compiler- und Sprachanbietereinstellungen Schema](index.md)
- [\<Compiler> Element](compiler-element.md)
