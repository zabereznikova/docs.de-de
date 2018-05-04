---
title: '&lt;System.CodeDom&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5939fa31a2f87348922d4586e3e7b7b52066fb09
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltsystemcodedomgt-element"></a>&lt;System.CodeDom&gt; Element
Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.  
  
 \<Konfiguration >-Element  
\<System.CodeDom > Element  
  
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
|[\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Der Container für Compilerkonfigurationselemente, dieser enthält 0 (null) oder mehr [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)-Elemente.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="net-framework-version-20"></a>.NET Framework, Version 2.0  
 Die [ \<system.codedom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) Element enthält compilerkonfigurationseinstellungen für Sprachenanbieter installiert, die auf einem Computer sowie die Standardanbieter, die mit .NET Framework, z. B. installiert sind die <xref:Microsoft.CSharp.CSharpCodeProvider> und <xref:Microsoft.VisualBasic.VBCodeProvider>. Die [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) -Element enthält 0 (null) oder mehrere [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) Elemente. Jede [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) Element gibt die compilerkonfigurationsattribute für eine bestimmte Sprache-Anbieter.  
  
 Entwickler und compileranbietern können Konfigurationseinstellungen Hinzufügen der Computerkonfigurationsdatei ("Machine.config") für einen neuen <xref:System.CodeDom.Compiler.CodeDomProvider> Implementierung. Verwenden der <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> Methode, um programmgesteuert aufzählen, die Language-Standardanbieter und der Sprachenanbieter identifiziert durch den Compiler-Konfigurationseinstellungen auf einem Computer.  
  
> [!NOTE]
>  In der .NET Framework-Versionen 1.0 und 1.1 kann die Standardsprache Anbietern von .NET Framework, in identifiziert werden der [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) Element. In .NET Framework, Version 2.0, werden nicht die Language-Standardanbieter identifiziert die [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) Element, aber aufgelistet werden kann, mit der <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> Methode.  
  
## <a name="net-framework-versions-10-and-11"></a>.NET Framework-Versionen 1.0 und 1.1  
 Die [ \<system.codedom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) Element enthält die compilereinstellungen für die Konfiguration für Sprachenanbieter auf einem Computer. Die [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) -Element enthält 0 (null) oder mehrere [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) Elemente. Jede [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) Element gibt die compilerkonfigurationsattribute für eine bestimmte Sprache-Anbieter.  
  
 .NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config). Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen. Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Computerkonfigurationsdatei und der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht eine typischen Compilerkonfiguration.  
  
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
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Compiler and Language Provider Settings Schema (Schema für Compiler- und Sprachanbietereinstellungen)](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)  
 [\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
