---
title: "&lt;etwEnable&gt;-Element | Microsoft Docs"
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
  - "<etwEnable>-Element"
  - "etwEnable-Element"
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;etwEnable&gt;-Element
Gibt an, ob die Ereignisablaufverfolgung für Windows \(ETW\) für Common Language Runtime\-Ereignisse aktiviert werden soll.  
  
## Syntax  
  
```  
<etwEnable enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob ETW aktiviert werden soll.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|true|ETW aktivieren.  Dies ist der Standard für Versionen von Windows ab den Betriebssystemen Windows Vista und Windows Server 2008.|  
|false|Deaktiviert ETW.  Dies ist der Standard für frühere Versionen von Windows.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Ab Windows Vista wird ETW standardmäßig aktiviert.  Verwenden Sie dieses Element, um ETW für eine Anwendung zu deaktivieren.  Verwenden Sie in früheren Versionen von Windows dieses Element, um ETW für eine Anwendung zu aktivieren.  
  
> [!NOTE]
>  ETW kann über eine Registrierungseinstellung auf einem Server global deaktiviert oder aktiviert werden.  Siehe [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md).  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie das ETW für eine Anwendung aktiviert wird.  
  
```  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md)