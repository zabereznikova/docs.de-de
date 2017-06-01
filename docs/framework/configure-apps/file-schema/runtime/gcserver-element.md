---
title: "&lt;gcServer&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<gcServer>-Element"
  - "gcServer-Element"
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# &lt;gcServer&gt;-Element
Gibt an, ob die Common Language Runtime die Garbage Collection auf dem Server ausführt.  
  
## Syntax  
  
```  
<gcServer    
   enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Runtime die Garbage Collection auf dem Server ausführt.|  
  
## Enabled\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|`false`|Die Garbage Collection wird nicht auf dem Server ausgeführt.  Dies ist die Standardeinstellung.|  
|`true`|Die Garbage Collection wird auf dem Server ausgeführt.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Die Common Language Runtime \(CLR\) unterstützt zwei Arten der Garbage Collection: die Garbage Collection auf der Arbeitsstation, die auf allen Systemen verfügbar ist, und die Garbage Collection auf dem Server, die auf Systemen mit mehreren Prozessoren verfügbar ist.  Mit dem `<gcServer>`\-Element steuern Sie die Art der von der CLR ausgeführten Garbage Collection.  Mithilfe der <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=fullName>\-Eigenschaft können Sie bestimmen, ob die Garbage Collection auf dem Server aktiviert ist.  
  
 Für Computer mit einem Prozessor stellt die Garbage Collection auf der Arbeitsstation \(Standardeinstellung\) in der Regel die schnellste Lösung dar.  Auf Computern mit zwei Prozessoren kann die Arbeitsstation\- oder die Serveroption verwendet werden.  Sind mehr als zwei Prozessoren vorhanden, stellt die Garbage Collection auf dem Server in der Regel die schnellste Lösung dar.  
  
 Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden. Wenn es in der Computerkonfigurationsdatei enthalten ist, wird es ignoriert.  
  
> [!NOTE]
>  In .NET Framework 4 und früheren Versionen ist die gleichzeitige Garbage Collection nicht verfügbar, wenn die Garbage Collection auf dem Server aktiviert ist.  Ab [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] erfolgt die Garbage Collection auf dem Server gleichzeitig.  Wenn die Garbage Collection auf dem Server nicht gleichzeitig erfolgen soll, legen Sie das `<gcServer>`\-Element auf `true` und das [\<gcConcurrent\>\-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) auf `false` fest.  
  
## Beispiel  
 Im folgenden Beispiel wird die Garbage Collection auf dem Server aktiviert.  
  
```  
  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
  
```  
  
## Siehe auch  
 <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=fullName>   
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [How to: Disable Concurrent Garbage Collection](http://msdn.microsoft.com/de-de/ba2c6c67-5778-497c-9fac-5f793b5500c7)