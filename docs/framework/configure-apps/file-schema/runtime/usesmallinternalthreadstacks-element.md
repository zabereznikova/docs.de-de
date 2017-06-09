---
title: "&lt;UseSmallInternalThreadStacks&gt;-Element | Microsoft Docs"
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
  - "<UseSmallInternalThreadStacks>-Element"
  - "UseSmallInternalThreadStacks-Element"
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;UseSmallInternalThreadStacks&gt;-Element
Fordert an, dass die Common Language Runtime \(CLR\) die Arbeitsspeicherverwendung reduziert, indem sie explizite Stapelgrößen beim Erstellen bestimmter Threads angibt, die intern verwendet werden, anstatt die Standardstapelgröße für diese Threads zu verwenden.  
  
## Syntax  
  
```  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob angefordert werden soll, dass bei der Erstellung bestimmter Threads, die intern verwendet werden, die CLR explizite Stapelgrößen statt der Standardstapelgröße verwendet.  Die expliziten Stapelgrößen sind kleiner als die Standardstapelgröße von 1 MB.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|true|Fordern Sie explizite Stapelgrößen an.|  
|false|Verwenden Sie die Standardstapelgröße.  Dies ist der Standard für [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Dieses Konfigurationselement dient zur Anforderung von geringerer Verwendung von virtuellem Arbeitsspeicher in einem Prozess, da die expliziten Threadgrößen, die die CLR für die internen Threads verwendet, wenn die Anforderung umgesetzt wird, kleiner als die Standardgröße sind.  
  
> [!IMPORTANT]
>  Dieses Konfigurationselement ist eine Anforderung an die CLR und keine absolute Anforderung.  In [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] wird die Anforderung nur für die x86\-Architektur berücksichtigt.  Dieses Element könnte in zukünftigen Versionen der CLR völlig ignoriert oder durch explizite Stapelgrößen ersetzt werden, die immer für ausgewählte interne Threads verwendet werden.  
  
 Das Angeben dieses Konfigurationselements tauscht Zuverlässigkeit gegen kleinere virtuelle Arbeitsspeicherverwendung ein, wenn die CLR die Anforderung berücksichtigt, da kleinere Stapelgrößen die Wahrscheinlichkeit für Stapelüberläufe potenziell vergrößern können.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie angefordert wird, dass die CLR explizite Stapelgrößen für bestimmte Threads verwenden, die intern verwendet werden.  
  
```  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)