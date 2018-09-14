---
title: '&lt;ApplicationPool&gt; -Element (Webeinstellungen)'
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1a129abca5888120d03c42689ac825d768733a9d
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45515638"
---
# <a name="ltapplicationpoolgt-element-web-settings"></a>&lt;ApplicationPool&gt; -Element (Webeinstellungen)
Gibt Konfigurationseinstellungen an, die von ASP.NET verwendet werden, um prozessübergreifende Verhalten zu verwalten, wenn eine ASP.NET-Anwendung im integrierten Modus ausgeführt wird, auf [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder eine höhere Version.  
  
> [!IMPORTANT]
>  Dieses Element und das Feature unterstützt es funktionieren nur, wenn auf Ihrer ASP.NET-Anwendung gehostet wird [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder höhere Versionen.  
  
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
|`maxConcurrentRequestsPerCPU`|Gibt an, wie viele gleichzeitige Anforderungen pro CPU ASP.NET erlaubt.|  
|`maxConcurrentThreadsPerCPU`|Gibt an, wie viele gleichzeitige Threads für jede CPU für einen Anwendungspool ausgeführt werden können. Dies bietet eine alternative Möglichkeit zum Steuern von ASP.NET Parallelität, da Sie die Anzahl der verwalteten Threads beschränken können, die pro CPU verwendet werden können, um Anforderungen zu verarbeiten. Standardmäßig ist diese Einstellung 0, d. h., dass ASP.NET die Anzahl der Threads pro CPU, erstellt werden können, die nicht begrenzt, obwohl die CLR-Threadpool auch die Anzahl der Threads beschränkt, die erstellt werden können.|  
|`requestQueueLimit`|Gibt die maximale Anzahl von Anforderungen, die für ASP.NET in einem einzigen Prozess in die Warteschlange eingereiht werden können. Wenn zwei oder mehr ASP.NET-Anwendungen in einen einzelnen Anwendungspool ausführen möchten, unterliegt die kumulative Satz von Anforderungen an jede Anwendung im Anwendungspool, der mit dieser Einstellung.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.web>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|Enthält Informationen zur Interaktion von ASP.NET mit einer hostanwendung.|  
  
## <a name="remarks"></a>Hinweise  
 Beim Ausführen von [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder eine höhere Version im integrierten Modus, diese Kombination Element können Sie konfigurieren, wie ASP.NET Anfragen von Threads und Warteschlangen verwaltet, wenn die Anwendung in einem IIS-Anwendungspool gehostet wird. Wenn Sie IIS 6 oder ausführen [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] im klassischen Modus oder im ISAPI-Modus, werden diese Einstellungen ignoriert.  
  
 Die `applicationPool` Einstellungen gelten für alle Anwendungspools, die auf eine bestimmte Version von .NET Framework ausgeführt. Die Einstellungen sind in einer Datei "aspnet.config" enthalten. Es gibt eine Version dieser Datei für die Versionen 2.0 und 4.0 von .NET Framework. (Die Versionen 3.0 und 3.5 von .NET Framework Freigeben der Datei "aspnet.config" mit Version 2.0.)  
  
> [!IMPORTANT]
>  Wenn das Ausführen [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] auf [!INCLUDE[win7](../../../../../includes/win7-md.md)], Sie können eine separate aspnet.config-Datei für jeden Anwendungspool konfigurieren. Dadurch können Sie die Leistung des Threads für jeden Anwendungspool anpassen.  
  
 Für die `maxConcurrentRequestsPerCPU` festlegen, die Standardeinstellung "5000" in der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] effektiv deaktiviert, eine Drosselung der Anforderungen von ASP.NET gesteuert, es sei denn, Sie tatsächlich 5000 oder mehrere Anforderungen pro CPU. Die Standardeinstellung hängt stattdessen die CLR-Threadpool Parallelität pro CPU automatisch verwaltet. Anwendungen, die machen umfassenden Gebrauch von der Verarbeitung von asynchronen Anforderungen oder viele lang andauernder Anforderungen, die Netzwerk-e/a blockiert deren, profitieren von der erhöhten Standardgrenzwert in die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]. Festlegen von `maxConcurrentRequestsPerCPU` auf 0 (null) deaktiviert die Verwendung von verwalteten Threads für die Verarbeitung von ASP.NET-Anforderungen. Wenn eine Anwendung in einem IIS-Anwendungspool ausgeführt wird, Anforderungen, die auf dem IIS-e/a-Thread bleiben und aus diesem Grund wird die Parallelität durch die Einstellungen der IIS-Thread gedrosselt.  
  
 Die `requestQueueLimit` Einstellung funktioniert genauso wie die `requestQueueLimit` Attribut der [ProcessModel](https://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) -Element, das in den Dateien "Web.config" für ASP.NET-Anwendungen festgelegt ist. Allerdings die `requestQueueLimit` Einstellung in einer Datei "aspnet.config" überschreibt die `requestQueueLimit` in einer Datei "Web.config" festlegen. Das heißt, wenn beide Attribute festgelegt werden (Dies wird standardmäßig "true"), die `requestQueueLimit` Einstellung in der Datei "aspnet.config" hat Vorrang vor.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie ASP.NET prozessübergreifende Verhalten in der Datei "aspnet.config" in den folgenden Situationen konfigurieren:  
  
-   Die Anwendung gehostet wird, eine [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] -Anwendungspool.  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] im integrierten Modus ausgeführt wird.  
  
-   Die Anwendung verwendet die [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] oder eine höhere Version.  
  
 Die Werte im Beispiel werden die Standardwerte.  
  
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
