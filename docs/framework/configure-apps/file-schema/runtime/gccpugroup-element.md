---
title: <GCCpuGroup> Element
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85cfe57f7a3b8cfecfae4c4ae00efaea464e6120
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090341"
---
# <a name="gccpugroup-element"></a>\<GCCpuGroup >-Element
Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.  
  
 \<configuration>  
\<runtime>  
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
 Wenn ein Computer über mehrere CPU-Gruppen verfügt und Garbagecollection auf dem Server aktiviert ist (finden Sie unter den [ \<GcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) Element), aktivieren dieses Element wird die Garbagecollection auf alle CPU-Gruppen, und nimmt alle Kerne in Beim Erstellen und Ausgleichen von Heaps-Konto.  
  
> [!NOTE]
>  Dieses Element gilt nur für Garbage Collection-Threads. Sie müssen auch aktivieren, um die Laufzeit zur Verteilung von Benutzerthreads auf alle CPU-Gruppen zu aktivieren, die [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) Element.  
  
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

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Zum Deaktivieren der gleichzeitigen Garbagecollection](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
