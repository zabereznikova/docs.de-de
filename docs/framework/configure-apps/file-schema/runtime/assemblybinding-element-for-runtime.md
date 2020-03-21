---
title: <assemblyBinding>-Element für <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
ms.openlocfilehash: 202b063ad3f0f9696cdc12aff434d61fe5a813e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154321"
---
# <a name="assemblybinding-element-for-runtime"></a>\<assemblyBinding> \<Element für Laufzeit>
Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<AssemblyBinding>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
      <assemblyBinding
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|**xmlns**|Erforderliches Attribut.<br /><br /> Gibt den XML-Namespace an, der für die Assemblybindung erforderlich ist. Verwenden Sie die Zeichenfolge "urn:schemas-microsoft-com:asm.v1" als Wert.|  
|**Appliesto**|Gibt die Laufzeitversion an, die für die .NET Framework-Assemblyumleitungen gilt. Dieses optionale Attribut verwendet eine .NET Framework-Versionsnummer, um anzugeben, welche Version verwendet wird. Ohne Angabe eines **appliesTo**-Attributs gilt das **\<assemblyBinding>**-Element für alle Versionen von .NET Framework. Das **attribut appliesTo** wurde in .NET Framework Version 1.1 eingeführt. es wird von der .NET Framework Version 1.0 ignoriert. Dies bedeutet, dass alle ** \<AssemblyBinding->-Elemente** angewendet werden, wenn .NET Framework Version 1.0 verwendet wird, auch wenn ein **appliesTo-Attribut** angegeben ist.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<dependentAssembly>](dependentassembly-element.md)|Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für eine Assembly. Verwenden Sie für jede Assembly ein ** \<abhängiges Assembly->-Tag.**|  
|[\<Prüfen>](probing-element.md)|Gibt Unterverzeichnisse an, die die Common Language Runtime beim Laden von Assemblys durchsucht.|  
|[\<publisherPolicy>](publisherpolicy-element.md)|Gibt an, ob die Common Language Runtime die Herausgeberrichtlinie anwendet.|  
|[\<qualifyAssembly>](qualifyassembly-element.md)|Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie eine Assemblyversion zu einer anderen umleiten und eine Codebasis bereitstellen.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Das folgende Beispiel zeigt, wie das **attribute appliesTo** verwendet wird, um die Bindung einer .NET Framework-Assembly umzuleiten.  
  
```xml  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Schema der Konfigurationsdatei](../index.md)
- [Umleiten von Assemblyversionen](../../redirect-assembly-versions.md)
