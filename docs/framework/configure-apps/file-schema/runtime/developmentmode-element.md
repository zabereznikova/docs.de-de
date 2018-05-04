---
title: '&lt;DevelopmentMode&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71b4eb1dfb50774cea2f7a50d5e5350b0338f41e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltdevelopmentmodegt-element"></a>&lt;DevelopmentMode&gt; Element
Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.  
  
 \<configuration>  
\<Common Language Runtime >  
\<DevelopmentMode >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**developerInstallation**|Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.|  
  
## <a name="developerinstallation-attribute"></a>developerInstallation-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**true**|Sucht nach Assemblys die DEVPATH-Umgebungsvariable angegebenen Verzeichnisse.|  
|**false**|Sucht nicht nach Assemblys die DEVPATH-Umgebungsvariable angegebenen Verzeichnisse. Dies ist die Standardeinstellung|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Einstellung nur zum Zeitpunkt der Entwicklung. Die Common Language Runtime überprüft nicht die Versionen auf Assemblys mit starkem Namen in die DEVPATH gefunden. Sie verwendet einfach die erste Assembly gefundenen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die dazu führen, dass die Common Language Runtime nach Assemblys die DEVPATH-Umgebungsvariable angegebenen Verzeichnisse suchen.  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Gewusst wie: Suchen von Assemblys mit DEVPATH](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)
