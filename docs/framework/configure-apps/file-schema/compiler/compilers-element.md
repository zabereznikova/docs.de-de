---
title: <compilers>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
ms.openlocfilehash: 1aa096e185ae7f5957f173c03e221a31f30d5200
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172943"
---
# <a name="compilers-element"></a>\<compilers>-Element

Container für Compilerkonfigurationselemente; enthält 0 (null) oder mehr- [\<compiler>](compiler-element.md) Elemente.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<compilers>**

## <a name="syntax"></a>Syntax  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  

 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<compiler>-Element](compiler-element.md)|Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<configuration>-Element](../configuration-element.md)|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|[\<system.codedom>-Element](system-codedom-element.md)|Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.|  
  
## <a name="remarks"></a>Bemerkungen  

 Das- [\<compilers>](compilers-element.md) Element enthält die Compilerkonfigurationseinstellungen für Sprachanbieter auf einem Computer. Jedes- [\<compiler>](compiler-element.md) Element gibt die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an.  
  
 In der .NET Framework werden die anfänglichen Compilereinstellungen und Sprachanbieter Einstellungen in der Computer Konfigurationsdatei (Machine.config) definiert. Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>-Implementierung hinzufügen. Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  

 Dieses Element kann in der Computer Konfigurationsdatei und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
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
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
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
- [\<compiler>-Element](compiler-element.md)
