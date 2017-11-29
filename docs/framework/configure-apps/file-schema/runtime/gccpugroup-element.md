---
title: '&lt;GCCpuGroup&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: abcb6d1b5f9dbb7a866b55628aabfe996a0a747c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltgccpugroupgt-element"></a>&lt;GCCpuGroup&gt; Element
Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.  
  
 \<configuration>  
\<Common Language Runtime >  
\<GCCpuGroup >  
  
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
 [Vorgehensweise: Deaktivieren der gleichzeitigen Garbagecollection](http://msdn.microsoft.com/en-us/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
 [Arbeitsstation und Server Garbagecollection](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
