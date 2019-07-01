---
title: <applicationPool>-Element (Webeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: d6c931ec904e9a7e58d5b747c74898208863b8e9
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486725"
---
# <a name="applicationpool-element-web-settings"></a>\<ApplicationPool >-Element (Webeinstellungen)
Gibt Konfigurationseinstellungen an, die von ASP.NET verwendet werden, um prozessübergreifende Verhalten zu verwalten, wenn eine ASP.NET-Anwendung unter IIS 7.0 oder höher im integrierten Modus ausgeführt wird.  
  
> [!IMPORTANT]
>  Dieses Element und das Feature unterstützt nur möglich, wenn Ihre ASP.NET-Anwendung auf IIS 7.0 oder höher gehostet wird.  
  
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
 Wenn Sie IIS 7.0 oder höher im integrierten Modus ausführen, Sie können diese Kombination Element konfigurieren, wie ASP.NET Anfragen von Threads und Warteschlangen verwaltet, wenn die Anwendung in einem IIS-Anwendungspool gehostet wird. Wenn Sie die IIS 6 ausführen oder Ausführen von IIS 7.0 im klassischen Modus oder im ISAPI-Modus, werden diese Einstellungen ignoriert.  
  
 Die `applicationPool` Einstellungen gelten für alle Anwendungspools, die auf eine bestimmte Version von .NET Framework ausgeführt. Die Einstellungen sind in einer Datei "aspnet.config" enthalten. Es gibt eine Version dieser Datei für die Versionen 2.0 und 4.0 von .NET Framework. (Die Versionen 3.0 und 3.5 von .NET Framework Freigeben der Datei "aspnet.config" mit Version 2.0.)  
  
> [!IMPORTANT]
>  Wenn Sie IIS 7.0 ausführen, auf [!INCLUDE[win7](../../../../../includes/win7-md.md)], Sie können eine separate aspnet.config-Datei für jeden Anwendungspool konfigurieren. Dadurch können Sie die Leistung des Threads für jeden Anwendungspool anpassen.  
  
 Für die `maxConcurrentRequestsPerCPU` festlegen, die Standardeinstellung "5000" in .NET Framework 4 effektiv deaktiviert eine Drosselung der Anforderungen, die von ASP.NET gesteuert wird, wenn Sie sich tatsächlich um 5000 oder mehrere Anforderungen pro CPU verfügen. Die Standardeinstellung hängt stattdessen die CLR-Threadpool Parallelität pro CPU automatisch verwaltet. Anwendungen, die machen umfassenden Gebrauch von der Verarbeitung von asynchronen Anforderungen oder viele lang andauernder Anforderungen, die Netzwerk-e/a blockiert deren, profitieren von der erhöhten Standardgrenzwert in .NET Framework 4. Festlegen von `maxConcurrentRequestsPerCPU` auf 0 (null) deaktiviert die Verwendung von verwalteten Threads für die Verarbeitung von ASP.NET-Anforderungen. Wenn eine Anwendung in einem IIS-Anwendungspool ausgeführt wird, Anforderungen, die auf dem IIS-e/a-Thread bleiben und aus diesem Grund wird die Parallelität durch die Einstellungen der IIS-Thread gedrosselt.  
  
 Die `requestQueueLimit` Einstellung funktioniert genauso wie die `requestQueueLimit` Attribut der [ProcessModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) -Element, das in den Dateien "Web.config" für ASP.NET-Anwendungen festgelegt ist. Allerdings die `requestQueueLimit` Einstellung in einer Datei "aspnet.config" überschreibt die `requestQueueLimit` in einer Datei "Web.config" festlegen. Das heißt, wenn beide Attribute festgelegt werden (Dies wird standardmäßig "true"), die `requestQueueLimit` Einstellung in der Datei "aspnet.config" hat Vorrang vor.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie ASP.NET prozessübergreifende Verhalten in der Datei "aspnet.config" in den folgenden Situationen konfigurieren:  
  
- Die Anwendung wird in einem Anwendungspool von IIS 7.0 gehostet.  
  
- IIS 7.0 wird im integrierten Modus ausgeführt.  
  
- Die Anwendung ist .NET Framework 3.5 SP1 oder höher verwenden.  
  
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

- [\<system.web>-Element (Webeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)
