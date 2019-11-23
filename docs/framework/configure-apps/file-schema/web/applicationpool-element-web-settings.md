---
title: <applicationPool>-Element (Webeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: c88f4e5407e550047eaf0f5c8d0d2924da611e93
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699225"
---
# <a name="applicationpool-element-web-settings"></a>\<ApplicationPool > Element (Webeinstellungen)
Gibt Konfigurationseinstellungen an, die von ASP.NET verwendet werden, um Prozess weites Verhalten zu verwalten, wenn eine ASP.NET-Anwendung im integrierten Modus unter IIS 7,0 oder einer höheren Version ausgeführt wird.  
  
> [!IMPORTANT]
> Dieses Element und die Funktion, die es unterstützt, funktionieren nur, wenn Ihre ASP.NET-Anwendung auf IIS 7,0 oder höher gehostet wird.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<System. Web >** ](system-web-element-web-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp; **\<ApplicationPool >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|Gibt an, wie viele gleichzeitige Anforderungen ASP.net pro CPU zulässt.|  
|`maxConcurrentThreadsPerCPU`|Gibt an, wie viele gleichzeitige Threads für einen Anwendungs Pool für jede CPU ausgeführt werden können. Dies bietet eine alternative Möglichkeit zum Steuern der ASP.net-Parallelität, da Sie die Anzahl verwalteter Threads, die pro CPU verwendet werden können, für die Verarbeitung von Anforderungen einschränken können. Diese Einstellung ist standardmäßig auf 0 festgelegt. Dies bedeutet, dass ASP.net die Anzahl der Threads, die pro CPU erstellt werden können, nicht einschränkt, obwohl der CLR-Thread Pool auch die Anzahl der Threads einschränkt, die erstellt werden können.|  
|`requestQueueLimit`|Gibt die maximale Anzahl von Anforderungen an, die in einem einzelnen Prozess in eine Warteschlange eingereiht werden können. Wenn mindestens zwei ASP.NET-Anwendungen in einem einzelnen Anwendungs Pool ausgeführt werden, unterliegt der kumulative Satz von Anforderungen, die an eine beliebige Anwendung im Anwendungs Pool vorgenommen werden, dieser Einstellung.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 None.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|Enthält Informationen dazu, wie ASP.net mit einer Host Anwendung interagiert.|  
  
## <a name="remarks"></a>Hinweise  

Wenn Sie IIS 7,0 oder eine höhere Version im integrierten Modus ausführen, können Sie mit dieser Element Kombination konfigurieren, wie ASP.NET Threads und Warteschlangen Anforderungen verwaltet, wenn die Anwendung in einem IIS-Anwendungs Pool gehostet wird. Wenn Sie IIS 6 ausführen oder IIS 7,0 im klassischen Modus oder im ISAPI-Modus ausführen, werden diese Einstellungen ignoriert.  
  
Die `applicationPool` Einstellungen gelten für alle Anwendungs Pools, die auf einer bestimmten Version des .NET Framework ausgeführt werden. Die Einstellungen sind in einer ASPNET. config-Datei enthalten. Es gibt eine Version dieser Datei für die Versionen 2,0 und 4,0 der .NET Framework. (In den Versionen 3,0 und 3,5 des .NET Framework wird die Datei Aspnet. config mit Version 2,0 gemeinsam genutzt.)  
  
> [!IMPORTANT]
> Wenn Sie IIS 7,0 auf [!INCLUDE[win7](../../../../../includes/win7-md.md)]ausführen, können Sie für jeden Anwendungs Pool eine separate ASPNET. config-Datei konfigurieren. Auf diese Weise können Sie die Leistung der Threads für jeden Anwendungs Pool anpassen.  
  
Für die `maxConcurrentRequestsPerCPU` Einstellung deaktiviert die Standardeinstellung "5000" in der .NET Framework 4 effektiv die Anforderungs Drosselung, die von ASP.net gesteuert wird, es sei denn, Sie haben tatsächlich mindestens 5000 Anforderungen pro CPU. Die Standardeinstellung hängt stattdessen vom CLR-Thread Pool ab, um Parallelität pro CPU automatisch zu verwalten. Anwendungen, die eine umfangreiche Verwendung asynchroner Anforderungs Verarbeitung oder viele Anforderungen mit langer Ausführungszeit in Netzwerk-e/a blockieren, profitieren von der erhöhten Standardgrenze in der .NET Framework 4. Wenn Sie `maxConcurrentRequestsPerCPU` auf NULL festlegen, wird die Verwendung verwalteter Threads für die Verarbeitung von ASP.NET-Anforderungen deaktiviert. Wenn eine Anwendung in einem IIS-Anwendungs Pool ausgeführt wird, bleiben Anforderungen im IIS-e/a-Thread erhalten. Daher wird die Parallelität durch IIS-Thread Einstellungen gedrosselt.  
  
Die `requestQueueLimit` Einstellung funktioniert auf dieselbe Weise wie das `requestQueueLimit`-Attribut des [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) -Elements, das in den Web. config-Dateien für ASP.NET-Anwendungen festgelegt ist. Die `requestQueueLimit` Einstellung in einer Datei "ASPNET. config" überschreibt jedoch die `requestQueueLimit` Einstellung in einer Web. config-Datei. Anders ausgedrückt: Wenn beide Attribute festgelegt sind (Standardmäßig ist dies true), hat die `requestQueueLimit` Einstellung in der Datei Aspnet. config Vorrang.  
  
## <a name="example"></a>Beispiel  

Im folgenden Beispiel wird gezeigt, wie Sie das Prozess weite Verhalten von ASP.net in der Datei Aspnet. config in den folgenden Situationen konfigurieren:  
  
- Die Anwendung wird in einem IIS 7,0-Anwendungs Pool gehostet.  
  
- IIS 7,0 wird im integrierten Modus ausgeführt.  
  
- Die Anwendung verwendet den .NET Framework 3,5 SP1 oder eine höhere Version.  
  
Bei den Werten im Beispiel handelt es sich um die Standardwerte.  
  
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
|Kann leer sein||  
  
## <a name="see-also"></a>Siehe auch

- [\<system.web>-Element (Webeinstellungen)](system-web-element-web-settings.md)
