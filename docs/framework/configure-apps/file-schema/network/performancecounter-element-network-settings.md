---
title: '&lt;PerformanceCounter&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5879614fd34fe645899f1b95f41e9b0675418292
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltperformancecountergt-element-network-settings"></a>&lt;PerformanceCounter&gt; -Element (Netzwerkeinstellungen)
Aktiviert oder deaktiviert Netzwerkleistungsindikatoren.  
  
 \<configuration>  
\<system.net>  
\<settings>  
\<performanceCounters>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Gibt an, ob die Netzwerkleistungsindikatoren aktiviert sind. Der Standardwert ist `false`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
 Netzwerkleistungsindikatoren müssen in der zu verwendenden Konfigurationsdatei aktiviert sein. Alle Netzwerkleistungsindikatoren werden mit einer einzelnen Einstellung in der Konfigurationsdatei aktiviert bzw. deaktiviert. Einzelne Netzwerkleistungsindikatoren können nicht aktiviert oder deaktiviert werden. Weitere Informationen zu bestimmten Netzwerkleistungsindikatoren finden Sie unter [Netzwerkleistungsindikatoren](http://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd).  
  
 Der Standardwert ist, dass Netzwerkleistungsindikatoren Leistungsindikatoren deaktiviert sind.  
  
 Die <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der **aktiviert** Attribut aus anwendbaren Konfigurationsdateien.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie konfigurieren die <xref:System.Net> und in verwandten Namespaces Netzwerkleistungsindikatoren zu aktivieren.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [Netzwerkleistungsindikatoren](http://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd)
