---
title: <Thread_UseAllCpuGroups>-Element
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 236953cc1a430a1dd2a2fbb633c7ef06e6ba200f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704686"
---
# <a name="threaduseallcpugroups-element"></a>\<Thread_UseAllCpuGroups >-Element
Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU-Gruppen verteilt werden.  
  
 \<configuration>  
\<runtime>  
<Thread_UseAllCpuGroups>  
  
## <a name="syntax"></a>Syntax  
  
```xml
<Thread_UseAllCpuGroups    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU-Gruppen verteilt werden.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Verwaltete Threads werden von der Laufzeit nicht auf mehrere CPU-Gruppen verteilt. Dies ist die Standardeinstellung.|  
|`true`|Von der Laufzeit verteilt verwaltete Threads auf mehrere CPU-Gruppen, wenn der Computer über mehrere CPU-Gruppen verfügt und die [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) -Element aktiviert ist.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn ein Computer über mehrere CPU-Gruppen verfügt, wird durch Aktivieren dieses Elements die Laufzeit angewiesen, verwaltete Threads auf alle CPU-Gruppen zu verteilen. Um dieses Feature verwenden zu können, müssen Sie auch aktivieren die [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) -Element, das wird die Garbagecollection auf alle CPU-Gruppen und alle Kerne berücksichtigt beim Erstellen und Ausgleichen von Heaps. Aktivieren der [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) -Elements erfordert das Aktivieren der [ \<GcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) Element. Wenn diese Elemente nicht aktiviert sind, hat das Aktivieren des Elements `<Thread_UseAllCpuGroups>` keine Auswirkungen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird dargestellt, wie Unterstützung für mehrere CPU-Gruppen aktiviert wird.  
  
```xml  
<configuration>  
   <runtime>  
      <Thread_UseAllCpuGroups enabled="true"/>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<GCCpuGroup >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)
