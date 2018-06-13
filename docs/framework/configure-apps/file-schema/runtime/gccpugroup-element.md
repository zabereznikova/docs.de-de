---
title: '&lt;GCCpuGroup&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4461667bdb47d410c857b4ac2c9dd268438a02f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744017"
---
# <a name="ltgccpugroupgt-element"></a>&lt;GCCpuGroup&gt; Element
Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.  
  
 \<configuration>  
\<Common Language Runtime >  
\<GCCpuGroup>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Garbage Collection unterstützt mehrere CPU-Gruppen nicht. Dies ist die Standardeinstellung.|  
|`true`|Bei Aktivierung auf dem Server werden mehrere CPU-Gruppen von Garbage Collection unterstützt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn ein Computer über mehrere CPU-Gruppen verfügt und Garbagecollection auf dem Server aktiviert ist (siehe die [ \<GcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) Element), aktivieren dieses Element wird die Garbagecollection auf alle CPU-Gruppen und alle Kerne in Konto beim Erstellen und Ausgleichen von Heaps.  
  
> [!NOTE]
>  Dieses Element gilt nur für Garbage Collection-Threads. Sie müssen auch aktivieren, um das Laufzeitmodul zum Verteilen von Benutzerthreads auf alle CPU-Gruppen zu aktivieren, die [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) Element.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das Aktivieren der Garbage Collection für mehrere CPU-Gruppen veranschaulicht.  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Vorgehensweise: Deaktivieren der gleichzeitigen Garbagecollection](http://msdn.microsoft.com/library/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
 [Arbeitsstation und Server Garbagecollection](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
