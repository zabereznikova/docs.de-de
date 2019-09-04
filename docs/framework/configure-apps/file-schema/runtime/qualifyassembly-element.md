---
title: <qualifyAssembly>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 581b19cf74dcb5c2d5c4a549847629503fe0b6ff
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252370"
---
# <a name="qualifyassembly-element"></a>\<qualifyAssembly-> Element
Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding->** ](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<qualifyAssembly>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`partialName`|Erforderliches Attribut.<br /><br /> Gibt den partiellen Namen der Assembly an, wie Sie im Code angezeigt wird.|  
|`fullName`|Erforderliches Attribut.<br /><br /> Gibt den vollständigen Namen der Assembly an, wie Sie im globalen Assemblycache angezeigt wird.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Das Aufrufen <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> der-Methode mit partiellen Assemblynamen bewirkt, dass der Common Language Runtime nur im Anwendungs Basisverzeichnis nach der Assembly sucht. Verwenden Sie das  **\<>-Element qualifyAssembly** in der Anwendungs Konfigurationsdatei, um die vollständigen Assemblyinformationen (Name, Version, öffentliches Schlüssel Token und Kultur) bereitzustellen, und bewirken Sie, dass die Common Language Runtime im globaler Assemblycache.  
  
 Das **FullName** -Attribut muss die vier Felder der Assemblyidentität enthalten: Name, Version, öffentliches Schlüssel Token und Kultur. Das **partialName** -Attribut muss teilweise auf eine Assembly verweisen. Sie müssen mindestens den Textnamen der Assembly angeben (der häufigste Fall), Sie können jedoch auch Version, öffentliches Schlüssel Token oder Kultur (oder eine beliebige Kombination der vier, aber nicht alle vier) einschließen. Der **partialName** muss mit dem in Ihrem-Befehl angegebenen Namen identisch sein. Beispielsweise können Sie nicht als `"math"` **partialName** -Attribut in der Konfigurationsdatei angeben und im `Assembly.Load("math, Version=3.3.3.3")` Code aufzurufen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der-Befehl `Assembly.Load("math")` logisch `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`aufgerufen.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [So sucht Common Language Runtime nach Assemblys](../../../deployment/how-the-runtime-locates-assemblies.md)
- [Teilassemblyverweise](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))
