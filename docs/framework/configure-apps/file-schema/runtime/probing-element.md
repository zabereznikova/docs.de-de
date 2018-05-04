---
title: '&lt;Probing&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing
- http://schemas.microsoft.com/.NetConfiguration/v2.0#probing
helpviewer_keywords:
- <probing> element
- container tags, <probing> element
- probing element
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cab16e83466b5954bfebac07dd79c9a8b5e4594
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltprobinggt-element"></a>&lt;Probing&gt; Element
Gibt Unterverzeichnisse der Anwendungsbasis für die common Language Runtime beim Laden von Assemblys für die Suche an.  
  
 \<configuration>  
\<Common Language Runtime >  
\<assemblyBinding>  
\<Probing >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`privatePath`|Erforderliches Attribut.<br /><br /> Gibt die Unterverzeichnisse des Basisverzeichnisses der Anwendung, die Assemblys enthalten können. Begrenzen Sie die einzelnen Unterverzeichnissen mit einem Semikolon.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Unterverzeichnisse der Anwendungsbasis angeben, die die Common Language Runtime nach Assemblys suchen soll.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Festlegen des Speicherortes einer Assembly](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
