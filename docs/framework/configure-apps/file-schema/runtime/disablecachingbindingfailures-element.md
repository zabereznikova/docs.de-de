---
title: <disableCachingBindingFailures> Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4893adaf528f1a9ef8fc8eab8027406fd8520cc2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159275"
---
# <a name="disablecachingbindingfailures-element"></a>\<DisableCachingBindingFailures >-Element
Gibt an, ob das Zwischenspeichern von Bindungsfehlern, die auftreten, da die Assembly nicht, durch die Überprüfung gefunden wurde zu deaktivieren.  
  
 \<Configuration >-Element  
\<Common Language Runtime >-Element  
\<disableCachingBindingFailures>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob das Zwischenspeichern von Bindungsfehlern, die auftreten, da die Assembly nicht, durch die Überprüfung gefunden wurde zu deaktivieren.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|0|Deaktivieren Sie nicht das Zwischenspeichern von Bindungsfehlern, die auftreten, da die Assembly durch Testen nicht gefunden wurde. Dies ist das Standardverhalten-Bindung ab .NET Framework, Version 2.0.|  
|1|Deaktivieren Sie das Zwischenspeichern von Bindungsfehlern, die auftreten, da die Assembly durch Testen nicht gefunden wurde. Diese Einstellung wird auf das Bindungsverhalten von .NET Framework, Version 1.1 zurückgesetzt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Ab .NET Framework, Version 2.0, ist das Standardverhalten für das Laden von Assemblys zum Zwischenspeichern von alle Bindungs- und beim Laden von Fehlern. D. h. wenn Versuch zum Laden einer Assembly ein Fehler auftritt, ein Fehler auf nachfolgende Anforderungen zum Laden der gleichen Assembly sofort ohne zu versuchen, um die Assembly zu suchen. Dieses Element deaktiviert, das Standardverhalten für die Bindung von Fehlern, die auftreten, da die Assembly nicht konnte, können Sie in den Suchpfad gefunden werden wird. Diese Fehler lösen <xref:System.IO.FileNotFoundException>.  
  
 Eine Bindung von Ladefehlern sind von diesem Element nicht betroffen und werden immer zwischengespeichert. Diese Fehler auftreten, da die Assembly wurde gefunden, aber nicht geladen werden konnte. Sie lösen <xref:System.BadImageFormatException> oder <xref:System.IO.FileLoadException>. Die folgende Liste enthält einige Beispiele für solche Fehler.  
  
-   Wenn Sie versuchen, das Laden eine Datei ist keine gültige Assembly, nachfolgende Versuche zum Laden der Assembly schlägt fehl, selbst wenn die ungültige Datei durch die richtige Assembly ersetzt wird.  
  
-   Wenn Sie versuchen, eine Assembly zu laden, die vom Dateisystem gesperrt ist, schlagen nachfolgende Versuche zum Laden der Assembly fehl, auch nach die Assembly durch das Dateisystem freigegeben wird.  
  
-   Wenn eine oder mehrere Versionen der Assembly, die Sie laden möchten befindet sich in den Suchpfad, aber die die angeforderte Version nicht untereinander ist, fehl nachfolgende Versuche, diese Version zu laden, auch wenn die richtige Version in den Suchpfad verschoben wird.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie das Zwischenspeichern von Assemblybindungsfehlern, die auftreten, da die Assembly nicht, durch die Überprüfung gefunden wurde zu deaktivieren.  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
