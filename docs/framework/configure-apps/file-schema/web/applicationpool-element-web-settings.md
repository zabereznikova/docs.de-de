---
title: <applicationPool>-Element (Webeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 6feaa801610fa0ffbbf47575f25aff29fa46a66c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152853"
---
# <a name="applicationpool-element-web-settings"></a>\<applicationPool>-Element (Webeinstellungen)
Gibt Konfigurationseinstellungen an, die von ASP.NET verwendet werden, um prozessweites Verhalten zu verwalten, wenn eine ASP.NET Anwendung im integrierten Modus unter IIS 7.0 oder einer späteren Version ausgeführt wird.  
  
> [!IMPORTANT]
> Dieses Element und die unterstützte Funktion funktionieren nur, wenn Ihre ASP.NET Anwendung in IIS 7.0 oder neueren Versionen gehostet wird.  
  
[**\<Konfiguration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<applicationPool
    maxConcurrentRequestsPerCPU="5000"
    maxConcurrentThreadsPerCPU="0"
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|Gibt an, wie viele gleichzeitige Anforderungen ASP.NET pro CPU zulässt.|  
|`maxConcurrentThreadsPerCPU`|Gibt an, wie viele gleichzeitige Threads für einen Anwendungspool für jede CPU ausgeführt werden können. Dies bietet eine alternative Möglichkeit, ASP.NET Parallelität zu steuern, da Sie die Anzahl der verwalteten Threads begrenzen können, die pro CPU verwendet werden können, um Anforderungen zu bedienen. Standardmäßig ist diese Einstellung 0, was bedeutet, dass ASP.NET die Anzahl der Threads, die pro CPU erstellt werden können, nicht beschränkt, obwohl der CLR-Threadpool auch die Anzahl der Threads begrenzt, die erstellt werden können.|  
|`requestQueueLimit`|Gibt die maximale Anzahl von Anforderungen an, die für ASP.NET in einem einzelnen Prozess in die Warteschlange gestellt werden können. Wenn zwei oder mehr ASP.NET Anwendungen in einem einzelnen Anwendungspool ausgeführt werden, unterliegt der kumulative Satz von Anforderungen, die an eine Anwendung im Anwendungspool gestellt werden, dieser Einstellung.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|Enthält Informationen darüber, wie ASP.NET mit einer Hostanwendung interagiert.|  
  
## <a name="remarks"></a>Bemerkungen  

Wenn Sie IIS 7.0 oder eine neuere Version im integrierten Modus ausführen, können Sie mit dieser Elementkombination konfigurieren, wie ASP.NET Threads und Warteschlangenanforderungen verwaltet, wenn die Anwendung in einem IIS-Anwendungspool gehostet wird. Wenn Sie IIS 6 oder IIS 7.0 im klassischen Modus oder im ISAPI-Modus ausführen, werden diese Einstellungen ignoriert.  
  
Die `applicationPool` Einstellungen gelten für alle Anwendungspools, die auf einer bestimmten Version von .NET Framework ausgeführt werden. Die Einstellungen sind in einer Datei aspnet.config enthalten. Es gibt eine Version dieser Datei für die Versionen 2.0 und 4.0 von .NET Framework. (Die Versionen 3.0 und 3.5 von .NET Framework teilen sich die Datei aspnet.config mit Version 2.0.)  
  
> [!IMPORTANT]
> Wenn Sie IIS 7.0 unter Windows 7 ausführen, können Sie für jeden Anwendungspool eine separate aspnet.config-Datei konfigurieren. Auf diese Weise können Sie die Leistung der Threads für jeden Anwendungspool anpassen.  
  
Für `maxConcurrentRequestsPerCPU` die Einstellung deaktiviert die Standardeinstellung "5000" in .NET Framework 4 effektiv die Anforderungseinschränkung, die von ASP.NET gesteuert wird, es sei denn, Sie haben tatsächlich 5000 oder mehr Anforderungen pro CPU. Die Standardeinstellung hängt stattdessen vom CLR-Threadpool ab, um die Parallelität pro CPU automatisch zu verwalten. Anwendungen, die die Verarbeitung asynchroner Anforderungen ausgiebig nutzen oder bei denen viele Langandauernanforderungen für Netzwerk-E/A blockiert sind, profitieren von dem erhöhten Standardlimit in .NET Framework 4. Wenn `maxConcurrentRequestsPerCPU` Sie auf Null setzen, wird die Verwendung von verwalteten Threads für die Verarbeitung ASP.NET Anforderungen deaktiviert. Wenn eine Anwendung in einem IIS-Anwendungspool ausgeführt wird, bleiben Anforderungen im IIS-E/A-Thread, und daher wird die Parallelität durch IIS-Threadeinstellungen gedrosselt.  
  
Die `requestQueueLimit` Einstellung funktioniert auf `requestQueueLimit` die gleiche Weise wie das Attribut des [processModel-Elements,](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) das in den Web.config-Dateien für ASP.NET Anwendungen festgelegt ist. Die `requestQueueLimit` Einstellung in einer Datei aspnet.config `requestQueueLimit` überschreibt die Einstellung jedoch in einer Web.config-Datei. Mit anderen Worten, wenn beide Attribute festgelegt sind (standardmäßig `requestQueueLimit` ist dies true), hat die Einstellung in der Datei aspnet.config Vorrang.  
  
## <a name="example"></a>Beispiel  

Das folgende Beispiel zeigt, wie ASP.NET prozessweiten Verhalten in der Datei aspnet.config unter den folgenden Umständen konfiguriert wird:  
  
- Die Anwendung wird in einem IIS 7.0-Anwendungspool gehostet.  
  
- IIS 7.0 wird im integrierten Modus ausgeführt.  
  
- Die Anwendung verwendet .NET Framework 3.5 SP1 oder eine neuere Version.  
  
Die Werte im Beispiel sind die Standardwerte.  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>Elementinformationen  
  
|||  
|-|-|  
|Namespace||  
|Name des Schemas||  
|Validierungsdatei||  
|Kann leer sein||  
  
## <a name="see-also"></a>Weitere Informationen

- [\<system.web> Element (Webeinstellungen)](system-web-element-web-settings.md)
