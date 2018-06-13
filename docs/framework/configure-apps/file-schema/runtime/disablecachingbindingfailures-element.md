---
title: '&lt;DisableCachingBindingFailures&gt; Element'
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
ms.openlocfilehash: 422888a595e8fdea01f9cb9d256830467d6822ac
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745678"
---
# <a name="ltdisablecachingbindingfailuresgt-element"></a>&lt;DisableCachingBindingFailures&gt; Element
Gibt an, ob das Zwischenspeichern von Assemblybindungsfehlern, die auftreten, da die Assembly nicht, durch die Überprüfung gefunden wurde zu deaktivieren.  
  
 \<Konfiguration >-Element  
\<Common Language Runtime >-Element  
\<DisableCachingBindingFailures >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob das Zwischenspeichern von Assemblybindungsfehlern, die auftreten, da die Assembly nicht, durch die Überprüfung gefunden wurde zu deaktivieren.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|0|Deaktivieren Sie nicht das Zwischenspeichern von Assemblybindungsfehlern, die auftreten, da die Assembly durch die Überprüfung nicht gefunden wurde. Dies ist das Standardverhalten-Bindung beginnend mit .NET Framework, Version 2.0.|  
|1|Deaktivieren Sie das Zwischenspeichern von Assemblybindungsfehlern, die auftreten, da die Assembly durch die Überprüfung nicht gefunden wurde. Diese Einstellung zurücksetzt, das Bindungsverhalten von .NET Framework, Version 1.1.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit .NET Framework, Version 2.0, ist das Standardverhalten für das Laden von Assemblys zum Zwischenspeichern aller binden und Laden von Fehlern. D. h., wenn ein Versuch zum Laden einer Assembly fehlschlägt, fehlschlagen, nachfolgende Anforderungen zum Laden der gleichen Assembly sofort ohne jeder Versuch, die Assembly gesucht werden soll. Dieses Element deaktiviert das Standardverhalten zum Binden von Fehlern, die auftreten, da die Assembly nicht im Überprüfungspfad gefunden werden konnte. Diese Fehler auslösen <xref:System.IO.FileNotFoundException>.  
  
 Einige binden und Laden von Fehlern sind nicht betroffen von diesem Element und immer zwischengespeichert wurden. Diese Fehler auftreten, da die Assembly wurde gefunden, aber nicht geladen werden konnte. Sie lösen <xref:System.BadImageFormatException> oder <xref:System.IO.FileLoadException>. Die folgende Liste enthält einige Beispiele für solche Fehler.  
  
-   Wenn Sie versuchen, Sie laden eine Datei ist keine gültige Assembly, nachfolgende Versuche zum Laden der Assembly schlägt fehl, selbst wenn die ungültige Datei durch die richtige Assembly ersetzt wird.  
  
-   Wenn Sie versuchen, eine Assembly zu laden, die durch das Dateisystem gesperrt ist, schlagen nachfolgende Versuche zum Laden der Assembly fehl, auch nachdem die Assembly vom Dateisystem freigegeben wird.  
  
-   Wenn eine oder mehrere Versionen der Assembly, die Sie laden möchten befindet sich in der Überprüfungspfad, aber die auf die angeforderte Version nicht untereinander ist, fehl nachfolgende Versuche, diese Version zu laden, auch wenn die richtige Version in den Suchpfad verschoben wird.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel veranschaulicht das Zwischenspeichern von Assemblybindungsfehlern, die auftreten, da die Assembly nicht, durch die Überprüfung gefunden wurde zu deaktivieren.  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
