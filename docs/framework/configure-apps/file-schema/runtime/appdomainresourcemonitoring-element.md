---
title: <appDomainResourceMonitoring>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 3c6092b6c34bb13c0ad0e66df2d3b7e65ac3de7e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154375"
---
# <a name="appdomainresourcemonitoring-element"></a>\<appDomainResourceMonitoring>-Element
Weist die Runtime zum Sammeln von Statistiken für alle Anwendungsdomänen im Prozess für die Lebensdauer des Prozesses an.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Laufzeit Statistiken für die Überwachung der Anwendungs Domänen Ressourcen sammelt.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|`true`|Statistiken für die Überwachung von Anwendungs Domänen Ressourcen werden gesammelt.|  
|`false`|Statistiken für die Überwachung von Anwendungs Domänen Ressourcen werden nicht erfasst.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die Ressourcenüberwachung für die Anwendungsdomäne ist über die verwaltete Anwendungs Domänen Klasse, die hostende [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) -Schnittstelle und die Ereignis Ablauf Verfolgung für Windows (ETW) verfügbar. Wenn die Überwachung aktiviert ist, werden Statistiken für alle Anwendungs Domänen im Prozess für die Lebensdauer des Prozesses erfasst.  
  
 Um die Überwachung aus verwaltetem Code zu aktivieren, verwenden Sie die- <xref:System.AppDomain.MonitoringIsEnabled%2A> Eigenschaft.  
  
 Dieses Konfigurationselement ist nur in den .NET Framework 4 und höher verfügbar.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie die Überwachung von Anwendungs Domänen Ressourcen aktivieren.  
  
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
- [Konfigurationsdateischema](../index.md)
