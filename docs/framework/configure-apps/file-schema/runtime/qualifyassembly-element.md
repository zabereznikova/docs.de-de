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
ms.openlocfilehash: 74e83900c68ab4b3fe01beb3f97657b0140d78ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153918"
---
# <a name="qualifyassembly-element"></a>\<qualifyAssembly> Element
Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<AssemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`partialName`|Erforderliches Attribut.<br /><br /> Gibt den Teilnamen der Assembly an, wie er im Code angezeigt wird.|  
|`fullName`|Erforderliches Attribut.<br /><br /> Gibt den vollständigen Namen der Assembly an, wie er im globalen Assemblycache angezeigt wird.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> Sie die Methode mithilfe partieller Assemblynamen aufrufen, wird die Common Language Runtime nur im Anwendungsbasisverzeichnis nach der Assembly suchen. Verwenden Sie das ** \<qualifyAssembly>-Element** in der Anwendungskonfigurationsdatei, um die vollständigen Assemblyinformationen (Name, Version, öffentliches Schlüsseltoken und Kultur) bereitzustellen und die Common Language-Laufzeit im globalen Assemblycache nach der Assembly zu suchen.  
  
 Das **fullName-Attribut** muss die vier Felder der Assemblyidentität enthalten: Name, Version, öffentliches Schlüsseltoken und Kultur. Das **partialName-Attribut** muss teilweise auf eine Assembly verweisen. Sie müssen mindestens den Textnamen der Assembly angeben (der häufigste Fall), aber Sie können auch Version, öffentliches Schlüsseltoken oder Kultur (oder eine beliebige Kombination der vier, aber nicht alle vier) einschließen. Der **partialName** muss mit dem in Ihrem Aufruf angegebenen Namen übereinstimmen. Sie können z. `"math"` B. nicht als **partielles Name-Attribut** in Ihrer Konfigurationsdatei und als Aufruf `Assembly.Load("math, Version=3.3.3.3")` im Code angeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird `Assembly.Load("math")` der `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`Aufruf logisch in .  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [So sucht die Laufzeit Assemblys](../../../deployment/how-the-runtime-locates-assemblies.md)
- [Partielle Assemblyverweise](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))
