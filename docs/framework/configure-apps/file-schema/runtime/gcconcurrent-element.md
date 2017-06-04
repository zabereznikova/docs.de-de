---
title: "&lt;gcConcurrent&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<gcConcurrent>-Element"
  - "Containertags, <gcConcurrent>-Element"
  - "gcConcurrent-Element"
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# &lt;gcConcurrent&gt;-Element
Gibt an, ob die Common Language Runtime die Garbage Collection auf einem separaten Thread ausführt.  
  
## Syntax  
  
```  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Runtime die Garbage Collection gleichzeitig ausführt.|  
  
## Enabled\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|`false`|Die Garbage Collection wird nicht gleichzeitig ausgeführt.|  
|`true`|Die Garbage Collection wird gleichzeitig ausgeführt.  Dies ist die Standardeinstellung.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Vor .NET Framework 4 unterstützt die Garbage Collection auf einer Arbeitsstation gleichzeitige Garbage Collection, bei der die Garbage Collection im Hintergrund auf einem separaten Thread ausgeführt wird.  In .NET Framework 4 wurde die gleichzeitige Garbage Collection durch die Garbage Collection im Hintergrund ersetzt, bei der die Garbage Collection ebenfalls im Hintergrund auf einem separaten Thread ausgeführt wird.  Ab .NET Framework 4.5 ist die Garbage Collection im Hintergrund für Garbage Collection auf dem Server verfügbar.  Das `<gcConcurrent>`\-Element steuert, ob die Runtime entweder gleichzeitige Garbage Collection oder Garbage Collection im Hintergrund ausführt, sofern diese verfügbar ist, oder ob die Runtime die Garbage Collection im Vordergrund ausführt.  
  
> [!WARNING]
>  Ab .NET Framework 4 wird die gleichzeitige Garbage Collection durch die Garbage Collection im Hintergrund ersetzt.  Die Begriffe *gleichzeitig* und *Hintergrund* werden in der .NET Framework\-Dokumentation synonym verwendet.  Um die Garbage Collection im Hintergrund zu deaktivieren, verwenden Sie das `<gcConcurrent>`\-Element wie in diesem Artikel beschrieben.  
  
 Standardmäßig verwendet die Runtime gleichzeitige Garbage Collection oder Garbage Collection im Hintergrund, die für Wartezeiten optimiert ist.  Wenn Ihre Anwendung intensive Benutzerinteraktion bedingt, belassen Sie die parallele Garbage Collection aktiviert, damit die Pausenzeiten der Anwendung für die Ausführung der Garbage Collection minimiert werden.  Wenn Sie das `enabled`\-Attribut des `<gcConcurrent>`\-Elements auf `false` festlegen, verwendet die Runtime die nicht\-parallele Garbage Collection, die für Durchsatz optimiert ist.  Die folgende Konfigurationsdatei deaktiviert die Garbage Collection im Hintergrund.  
  
```xml  
  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
  
```  
  
 Gibt es eine `<gcConcurrentSetting>`\-Einstellung in der Computerkonfigurationsdatei, legt diese den Standardwert für alle .NET Framework\-Anwendungen fest.  Die Einstellung in der Computerkonfigurationsdatei setzt die Einstellung in der Anwendungskonfigurationsdatei außer Kraft.  
  
 Weitere Informationen zur gleichzeitigen Garbage Collection und zur Garbage Collection im Hintergrund finden Sie im Abschnitt "Gleichzeitige Garbage Collection" im Thema [Fundamentals of Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md).  
  
## Beispiel  
 Im folgenden Beispiel wird die gleichzeitige Garbage Collection aktiviert.  
  
```  
  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Fundamentals of Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md)