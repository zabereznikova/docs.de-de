---
title: "&lt;performanceCounters&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<performanceCounter>-Element"
  - "performanceCounter-Element"
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;performanceCounters&gt;-Element (Netzwerkeinstellungen)
Aktiviert oder deaktiviert Netzwerkleistungsindikatoren.  
  
## Syntax  
  
```  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Gibt an, ob die Netzwerkleistungsindikatoren aktiviert sind.  Der Standardwert ist `false`.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>\-Namespace.|  
  
## Hinweise  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
 Netzwerkleistungsindikatoren müssen zur Verwendung in der Konfigurationsdatei aktiviert werden.  Alle Netzwerkleistungsindikatoren werden mit einer einzelnen Einstellung in der Konfigurationsdatei aktiviert oder deaktiviert.  Einzelne Netzwerkleistungsindikatoren können nicht aktiviert oder deaktiviert werden.  Weitere Informationen zu den bestimmten Netzwerkleistungsindikatoren finden Sie unter [Networking Performance Counters](http://msdn.microsoft.com/de-de/d1860235-f643-46ae-846c-ff0ed8b0e3cd).  
  
 Der Standardwert ist, dass Netzwerkleistungsindikatoren deaktiviert sind.  
  
 Die <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=fullName>\-Eigenschaft kann verwendet werden, um den aktuellen Wert des **enabled**\-Attributs aus anwendbaren Konfigurationsdateien abzurufen.  
  
## Beispiel  
 Im folgenden Codebeispiel wird gezeigt, wie <xref:System.Net> und verwandte Namespaces konfiguriert werden, um Netzwerkleistungsindikatoren zu aktivieren.  
  
```  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=fullName>   
 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=fullName>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [Networking Performance Counters](http://msdn.microsoft.com/de-de/d1860235-f643-46ae-846c-ff0ed8b0e3cd)