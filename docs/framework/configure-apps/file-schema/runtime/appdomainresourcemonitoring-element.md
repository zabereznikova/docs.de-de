---
title: <appDomainResourceMonitoring>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 3c6092b6c34bb13c0ad0e66df2d3b7e65ac3de7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154375"
---
# <a name="appdomainresourcemonitoring-element"></a>\<appDomainResourceMonitoring> Element
Weist die Runtime zum Sammeln von Statistiken für alle Anwendungsdomänen im Prozess für die Lebensdauer des Prozesses an.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Laufzeit Statistiken für die Überwachung von Anwendungsdomänenressourcen sammelt.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|value|Beschreibung|  
|-----------|-----------------|  
|`true`|Statistiken für die Überwachung von Anwendungsdomänenressourcen werden gesammelt.|  
|`false`|Statistiken für die Überwachung von Anwendungsdomänenressourcen werden nicht erfasst.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die Überwachung von Anwendungsdomänenressourcen ist über die Domänenklasse der verwalteten Anwendung, die [ICLRAppDomainResourceMonitor-Schnittstelle](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) und die Ereignisablaufverfolgung für Windows (ETW) verfügbar. Wenn die Überwachung aktiviert ist, werden Statistiken für alle Anwendungsdomänen im Prozess für die Gesamteingang des Prozesses gesammelt.  
  
 Verwenden Sie die Eigenschaft, <xref:System.AppDomain.MonitoringIsEnabled%2A> um die Überwachung von verwaltetem Code zu aktivieren.  
  
 Dieses Konfigurationselement ist nur in .NET Framework 4 und höher verfügbar.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie die Überwachung von Anwendungsdomänenressourcen aktiviert wird.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [Schema für Laufzeiteinstellungen](index.md)
- [Schema der Konfigurationsdatei](../index.md)
