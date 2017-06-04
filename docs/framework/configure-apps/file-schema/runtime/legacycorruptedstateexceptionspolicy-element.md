---
title: "&lt;legacyCorruptedStateExceptionsPolicy&gt;-Element | Microsoft Docs"
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
  - "<legacyCorruptedStateExceptionsPolicy>-Element"
  - "legacyCorruptedStateExceptionsPolicy-Element"
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;legacyCorruptedStateExceptionsPolicy&gt;-Element
Gibt an, ob die Common Language Runtime zulässt, dass Zugriffsverletzungen und andere beschädigte Zustandsausnahmen von verwaltetem Code abgefangen werden.  
  
## Syntax  
  
```  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, dass Fehler aufgrund von beschädigten Zustandsausnahmen, beispielsweise Zugriffsverletzungen, von der Anwendung abgefangen werden.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|Fehler aufgrund von beschädigten Zustandsausnahmen, beispielsweise Zugriffsverletzungen, werden von der Anwendung nicht abgefangen.  Dies ist der Standardwert.|  
|`true`|Fehler aufgrund von beschädigten Zustandsausnahmen, beispielsweise Zugriffsverletzungen, werden von der Anwendung abgefangen.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 In .NET Framework und älteren Versionen ermöglichte die Common Language Runtime das Abfangen von Ausnahmen durch verwalteten Code, die von beschädigten Prozesszuständen ausgelöst wurden.  Eine Zugriffsverletzung ist ein Beispiel für diesen Ausnahmetyp.  
  
 Ab [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] werden diese Ausnahmetypen nicht mehr von verwaltetem Code in `catch`\-Blöcken abgefangen.  Sie können diese Änderung jedoch überschreiben und die Behandlung von beschädigten Zustandsausnahmen beibehalten. Dazu stehen Ihnen zwei Möglichkeiten zur Verfügung:  
  
-   Legen Sie im `<legacyCorruptedStateExceptionsPolicy>`\-Element das `enabled`\-Attribut auf `true` fest.  Diese Konfigurationseinstellung ist wird prozessweit übernommen und wirkt sich auf alle Methoden aus.  
  
 \- oder \-  
  
-   Wenden Sie das <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName>\-Attribut auf die Methode an, die die `catch`\-Ausnahmeblöcke enthält.  
  
 Dieses Konfigurationselement ist erst ab [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] verfügbar.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie angegeben wird, dass das Verhalten vor [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] von der Anwendung wiederhergestellt und alle Fehler aufgrund beschädigter Zustandsausnahmen abgefangen werden sollen.  
  
```  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>   
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)