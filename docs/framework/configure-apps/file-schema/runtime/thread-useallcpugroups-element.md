---
title: "&lt;Thread_UseAllCpuGroups&gt;-Element | Microsoft Docs"
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
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# &lt;Thread_UseAllCpuGroups&gt;-Element
Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU\-Gruppen verteilt werden.  
  
## Syntax  
  
```vb  
<Thread_UseAllCpuGroups    
   enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU\-Gruppen verteilt werden.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|Verwaltete Threads werden von der Laufzeit nicht auf mehrere CPU\-Gruppen verteilt.  Dies ist der Standardwert.|  
|`true`|Verwaltete Threads werden von der Laufzeit auf mehrere CPU\-Gruppen verteilt, wenn der Computer über mehrere CPU\-Gruppen verfügt und das [\<GCCpuGroup\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)\-Element aktiviert ist.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Wenn ein Computer über mehrere CPU\-Gruppen verfügt, wird durch Aktivieren dieses Elements die Laufzeit angewiesen, verwaltete Threads auf alle CPU\-Gruppen zu verteilen.  Um diese Funktion verwenden zu können, müssen Sie auch das [\<GCCpuGroup\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)\-Element aktivieren. Damit wird die Garbage Collection auf alle CPU\-Gruppen ausgedehnt, und beim Erstellen und Ausgleichen von Heaps werden alle Kerne berücksichtigt.  Das Aktivieren des [\<GCCpuGroup\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)\-Elements erfordert das Aktivieren des [\<gcServer\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)\-Elements.  Wenn diese Elemente nicht aktiviert sind, hat das Aktivieren des Elements `<Thread_UseAllCpuGroups>` keine Auswirkungen.  
  
## Beispiel  
 Im folgenden Beispiel wird dargestellt, wie Unterstützung für mehrere CPU\-Gruppen aktiviert wird.  
  
```  
<configuration>  
   <runtime>  
      <Thread_UseAllCpuGroups enabled="true"/>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<GCCpuGroup\>\-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)