---
title: "&lt;NetFx40_PInvokeStackResilience&gt;-Element | Microsoft Docs"
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
  - "<NetFx40_PInvokeStackResilience>-Element"
  - "NetFx40_PInvokeStackResilience-Element"
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;NetFx40_PInvokeStackResilience&gt;-Element
Gibt an, ob die Laufzeit falsche Plattformaufrufdeklarationen automatisch zur Laufzeit korrigiert, was zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code führt.  
  
## Syntax  
  
```  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Laufzeit falsche Plattformaufrufdeklarationen erkennt und den Stapel zur Laufzeit auf 32\-Bit\-Plattformen automatisch korrigiert.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`0`|Die Laufzeit verwendet die schnellere Interop\-Marshalling\-Architektur, die in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] eingeführt wurde und keine falschen Plattformaufrufdeklarationen erkennt und korrigiert.  Dies ist der Standardwert.|  
|`1`|Die Laufzeit verwendet langsamere Übergänge, die falsche Plattformaufrufdeklarationen erkennen und korrigieren.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## Hinweise  
 Dieses Element ermöglicht es Ihnen, schnelleres Interop\-Marshalling gegen falsche Plattformaufrufdeklarationen für Laufzeitnachgiebigkeit zu tauschen.  
  
 Beginnend mit dem [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] stellt eine stromlinienförmige Interop\-Marshalling\-Architektur eine bedeutende Leistungsverbesserung für Übergänge von verwaltetem Code zu nicht verwaltetem Code bereit.  In früheren Versionen von .NET Framework hat die Marshallingebene falsche Plattformaufrufdeklarationen auf 32\-Bit\-Plattformen erkannt und den Stapel automatisch korrigiert.  Die neue Marshallingarchitektur schließt diesen Schritt aus.  Als Ergebnis sind Übergänge sehr schnell, aber eine falsche Plattformaufrufdeklaration kann einen Programmfehler verursachen.  
  
 Damit Sie während der Entwicklung falsche Deklarationen leichter erkennen, wurde die Visual Studio\-Debugerfahrung verbessert.  Der von [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) verwaltete Debugging\-Assistent \(MDA\) benachrichtigt Sie über falschen Plattformaufrufdeklarationen, wenn die Anwendung mit angefügtem Debugger ausgeführt wird.  
  
 Um Szenarien zu behandeln, in denen die Anwendung Komponenten verwendet, die Sie nicht neu kompilieren können, und die falsche Plattformaufrufdeklarationen haben, können Sie das `NetFx40_PInvokeStackResilience`\-Element verwenden.  Dieses Element mit `enabled="1"` zur Anwendungskonfigurationsdatei hinzuzufügen wechselt in einen Kompatibilitätsmodus mit dem Verhalten der früheren Versionen von .NET Framework, bei dem langsamere Übergänge in Kauf genommen werden müssen.  Assemblys, die gegen frühere Versionen von .NET Framework kompiliert wurden, haben automatisch in diesen Kompatibilitätsmodus gewechselt und benötigen dieses Element nicht.  
  
## Konfigurationsdatei  
 Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie für erhöhte Nachgiebigkeit gegen falsche Plattformaufrufdeklarationen für eine Anwendung entschieden wird, was zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code führt.  
  
```  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)