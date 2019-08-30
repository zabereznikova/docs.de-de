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
ms.openlocfilehash: 19f37095bd01b76fda8b1e29423c413dbdb06a65
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168914"
---
# <a name="systemcodedom-element"></a>\<System. CodeDom >-Element
Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp; **\<System. CodeDom->**  
  
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
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<compilers>](compilers-element.md)|Der Container für Compilerkonfigurationselemente, dieser enthält 0 (null) oder mehr [\<compiler>](compiler-element.md)-Elemente.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="net-framework-version-20"></a>.NET Framework Version 2,0  
 <xref:Microsoft.CSharp.CSharpCodeProvider> [ Das\<System. CodeDom >](system-codedom-element.md) -Element enthält zusätzlich zu den Standard Anbietern, die mit dem .NET Framework installiert werden, Compilerkonfigurationseinstellungen für Sprachanbieter, die auf einem Computer installiert sind, wie z. b. und. <xref:Microsoft.VisualBasic.VBCodeProvider>. [ \<](compiler-element.md) [ Die\<Compiler >](compilers-element.md) -Elements enthalten keine oder mehrere Compiler>-Elemente. [ Jedes\<Compiler >](compiler-element.md) -Element gibt die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an.  
  
 Entwickler und Compileranbieter können der Computer Konfigurationsdatei (Machine. config) für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider> Implementierung Konfigurationseinstellungen hinzufügen. Verwenden Sie <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> die-Methode, um die Standard Sprachanbieter und Sprachanbieter, die von den Compilerkonfigurationseinstellungen eines Computers identifiziert werden, Programm gesteuert aufzuzählen.  
  
> [!NOTE]
> In den .NET Framework Versionen 1,0 und 1,1 werden die von der .NET Framework bereitgestellten Standard Sprachanbieter im [ \<Compiler >](compilers-element.md) -Element identifiziert. In der .NET Framework Version 2,0 werden die Standard Sprachanbieter nicht im [ \<Compiler >](compilers-element.md) Element identifiziert, können aber mithilfe der <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> -Methode aufgelistet werden.  
  
## <a name="net-framework-versions-10-and-11"></a>.NET Framework Versionen 1,0 und 1,1  
 [ Das\<System. CodeDom->](system-codedom-element.md) -Element enthält die Compilerkonfigurationseinstellungen für Sprachanbieter auf einem Computer. [ \<](compiler-element.md) [ Die\<Compiler >](compilers-element.md) -Elements enthalten keine oder mehrere Compiler>-Elemente. [ Jedes\<Compiler >](compiler-element.md) -Element gibt die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an.  
  
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
- [Compiler and Language Provider Settings Schema (Schema für Compiler- und Sprachanbietereinstellungen)](index.md)
- [\<compiler> Element](compiler-element.md)
