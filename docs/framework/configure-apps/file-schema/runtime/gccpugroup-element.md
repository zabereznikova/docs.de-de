---
title: "&lt;GCCpuGroup&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<GCCpuGroup>-Element"
  - "GCCpuGroup-Element"
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# &lt;GCCpuGroup&gt;-Element
Gibt an, ob von der Garbage Collection mehrere CPU\-Gruppen unterstützt werden.  
  
## Syntax  
  
```  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob von der Garbage Collection mehrere CPU\-Gruppen unterstützt werden.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|Garbage Collection unterstützt mehrere CPU\-Gruppen nicht.  Dies ist der Standardwert.|  
|`true`|Bei Aktivierung auf dem Server werden mehrere CPU\-Gruppen von Garbage Collection unterstützt.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Wenn ein Computer über mehrere CPU\-Gruppen verfügt und Garbage Collection auf dem Server aktiviert ist \(siehe das [\<gcServer\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)\-Element\), wird die Garbage Collection mit Aktivierung dieses Elements auf alle CPU\-Gruppen erweitert, und beim Erstellen und Ausgleichen von Heaps werden alle Kerne berücksichtigt.  
  
> [!NOTE]
>  Dieses Element gilt nur für Garbage Collection\-Threads.  Um die Verteilung von Benutzerthreads auf alle CPU\-Gruppen zur Laufzeit zu ermöglichen, müssen Sie auch das [\<Thread\_UseAllCpuGroups\>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)\-Element aktivieren.  
  
## Beispiel  
 Im folgenden Beispiel wird das Aktivieren der Garbage Collection für mehrere CPU\-Gruppen veranschaulicht.  
  
```  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [How to: Disable Concurrent Garbage Collection](http://msdn.microsoft.com/de-de/ba2c6c67-5778-497c-9fac-5f793b5500c7)   
 [Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)