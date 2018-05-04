---
title: '&lt;ApplicationPool&gt; Element (Webeinstellungen)'
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a2eafc6b5ad1446fd07518f877a8ec001ad8dbd6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltapplicationpoolgt-element-web-settings"></a>&lt;ApplicationPool&gt; Element (Webeinstellungen)
Gibt Konfigurationseinstellungen an, die von ASP.NET verwendet werden, prozessübergreifende Verhalten zu verwalten, wenn eine ASP.NET-Anwendung im integrierten Modus ausgeführt wird, auf [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder eine höhere Version.  
  
> [!IMPORTANT]
>  Dieses Element und das Feature unterstützt es nur möglich, wenn von Ihrer ASP.NET-Anwendung gehostet wird [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder höhere Versionen.  
  
 \<configuration>  
\<System.Web >-Element (Webeinstellungen)  
\<ApplicationPool >-Element (Webeinstellungen)  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|Gibt an, wie viele gleichzeitige Anforderungen pro CPU ASP.NET ermöglicht.|  
|`maxConcurrentThreadsPerCPU`|Gibt an, wie viele gleichzeitige Threads für jede CPU für einen Anwendungspool ausgeführt werden können. Dies bietet eine alternative Möglichkeit zum ASP.NET-Parallelität zu steuern, da Sie die Anzahl der verwalteten Threads einschränken können, die zum Verarbeiten von Anforderungen pro CPU verwendet werden kann. Standardmäßig ist diese Einstellung 0, was bedeutet, dass ASP.NET die Anzahl der Threads, die pro-CPU, erstellt werden, können nicht beschränkt, obwohl der CLR-Threadpool auch die Anzahl der Threads beschränkt, die erstellt werden können.|  
|`requestQueueLimit`|Gibt die maximale Anzahl von Anforderungen, die für ASP.NET in einem einzelnen Prozess in die Warteschlange eingereiht werden können. Wenn zwei oder mehr ASP.NET-Anwendungen in einen einzelnen Anwendungspool ausführen, wird diese Einstellung die kumulative Satz von Anforderungen an Anwendungen im Anwendungspool unterliegt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.web>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|Enthält Informationen zur Interaktion von ASP.NET mit einer hostanwendung.|  
  
## <a name="remarks"></a>Hinweise  
 Bei der Ausführung [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder eine höhere Version im integrierten Modus, der Kombination aus diesem Element können Sie konfigurieren, wie ASP.NET Threads und Warteschlangen Anforderungen verwaltet, wenn die Anwendung in einem IIS-Anwendungspool gehostet wird. Wenn Sie IIS 6 oder ausführen [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] im klassischen Modus oder im ISAPI-Modus, werden diese Einstellungen ignoriert.  
  
 Die `applicationPool` Einstellungen gelten für alle Anwendungspools, die auf eine bestimmte Version von .NET Framework ausgeführt. Die Einstellungen sind in einer aspnet.config-Datei enthalten. Es ist eine Version dieser Datei für die Versionen 2.0 und 4.0 von .NET Framework. (Die Versionen 3.0 und 3.5 von .NET Framework Serverfreigabe aspnet.config-Datei mit Version 2.0.)  
  
> [!IMPORTANT]
>  Wenn das Ausführen [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] auf [!INCLUDE[win7](../../../../../includes/win7-md.md)], können Sie eine separate aspnet.config-Datei für jeden Anwendungspool konfigurieren. Dadurch können Sie die Leistung des Threads für jeden Anwendungspool individuell anzupassen.  
  
 Für die `maxConcurrentRequestsPerCPU` festlegen, die Standardeinstellung von "5000" in der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] effektiv deaktiviert eine Einschränkung der Anforderungsanzahl also von ASP.NET gesteuert, es sei denn, Sie tatsächlich 5000 oder mehrere Anforderungen pro CPU haben. Die Standardeinstellung hängt stattdessen die CLR-Threadpool pro CPU Parallelität automatisch verwaltet. Anwendungen, die umfassenden Gebrauch von der Verarbeitung von asynchronen Anforderungen stellen oder bei denen viele langer-Anforderungen, die Netzwerk-e/a blockiert, ist, profitieren die erhöhte Standardgrenze in der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]. Festlegen von `maxConcurrentRequestsPerCPU` auf 0 (null) deaktiviert die Verwendung von verwalteten Threads für die Verarbeitung von ASP.NET-Anforderungen. Wenn eine Anwendung in einem IIS-Anwendungspool ausgeführt wird, bleiben Sie Anforderungen im IIS-e/a-Thread, und daher Parallelität von IIS-Thread-Einstellungen eingeschränkt wird.  
  
 Die `requestQueueLimit` Einstellung funktioniert genauso wie die `requestQueueLimit` Attribut von der [ProcessModel](http://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) Element, das in den Dateien "Web.config" für ASP.NET-Anwendungen festgelegt ist. Allerdings die `requestQueueLimit` Einstellung in einer aspnet.config-Datei überschreibt die `requestQueueLimit` in einer Datei "Web.config" festlegen. Das heißt, wenn beide Attribute festgelegt werden (Dies wird standardmäßig "true"), die `requestQueueLimit` Einstellung in aspnet.config-Datei hat Vorrang vor.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die zum Konfigurieren von ASP.NET prozessübergreifende Verhalten in aspnet.config-Datei in den folgenden Situationen:  
  
-   Die Anwendung gehostet wird, eine [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] Anwendungspool.  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] im integrierten Modus ausgeführt wird.  
  
-   Die Anwendung verwendet die [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] oder eine höhere Version.  
  
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
|Schemaname||  
|Validierungsdatei||  
|Leer kann sein||  
  
## <a name="see-also"></a>Siehe auch  
 [\<system.web>-Element (Webeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)
