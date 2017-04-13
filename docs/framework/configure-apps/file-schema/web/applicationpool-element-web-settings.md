---
title: "&lt;applicationPool&gt;-Element (Webeinstellungen) | Microsoft Docs"
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
  - "<applicationPool>-Element"
  - "applicationPool-Element"
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# &lt;applicationPool&gt;-Element (Webeinstellungen)
Gibt Konfigurationseinstellungen an, die von ASP.NET zur Verwaltung von prozessweitem Verhalten verwendet werden, wenn eine ASP.NET\-Anwendung in [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder in einer höheren Version im integrierten Modus ausgeführt wird.  
  
> [!IMPORTANT]
>  Dieses Element und die unterstützte Funktion können nur verwendet werden, wenn die ASP.NET\-Anwendung in [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder in einer höheren Versionen gehostet wird.  
  
## Syntax  
  
```  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`maxConcurrentRequestsPerCPU`|Gibt an, wie viele gleichzeitigen Anforderungen von ASP.NET pro CPU zugelassen werden.|  
|`maxConcurrentThreadsPerCPU`|Gibt an, wie viel Threads pro CPU gleichzeitig für einen Anwendungspool ausgeführt werden können.  Dies stellt eine alternative Möglichkeit zur Steuerung der ASP.NET\-Parallelität dar, da Sie die Anzahl der verwalteten Threads einschränken können, die pro CPU zur Behandlung von Anforderungen verwendet werden.  Die Standardeinstellung ist 0. Dies bedeutet, dass ASP.NET die Anzahl der Threads nicht einschränkt, die pro CPU erstellt werden können, obwohl die Anzahl der Threads, die erstellt werden können, auch vom CLR\-Threadpool eingeschränkt wird.|  
|`requestQueueLimit`|Gibt die maximale Anzahl der Anforderungen an, die in einen einzelnen Prozess für ASP.NET in die Warteschlange gestellt werden können.  Bei zwei oder mehr ASP.NET\-Anwendungen, die in einem Einzelanwendungspool ausgeführt werden, ist der kumulative Satz von Anforderungen, die an eine Anwendung im Anwendungspool gestellt werden, abhängig von dieser Einstellung.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<system.web\>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|Enthält Informationen darüber, wie ASP.NET mit einer Hostanwendung interagiert.|  
  
## Hinweise  
 Wenn Sie [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder eine höhere Version im integrierten Modus ausführen, können Sie mit dieser Elementkombination angeben, wie ASP.NET Threads verwaltet und Anforderungen in die Warteschlange stellt, wenn die Anwendung in einem IIS\-Anwendungspool gehostet wird.  Wenn Sie IIS 6 oder [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] im klassischen Modus oder im ISAPI\-Modus ausführen, werden diese Einstellungen ignoriert.  
  
 Die `applicationPool`\-Einstellungen gelten für alle Anwendungspools, die in einer bestimmten Version von .NET Framework ausgeführt werden.  Die Einstellungen sind in einer aspnet.config\-Datei enthalten.  Diese Datei ist für .NET Framework, Version 2.0 und 4, verfügbar. \(In .NET Framework, Version 3.0 und 3.5, wird die aspnet.config\-Datei für Version 2.0 verwendet.\)  
  
> [!IMPORTANT]
>  Wenn Sie [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] unter [!INCLUDE[win7](../../../../../includes/win7-md.md)] ausführen, können Sie eine separate aspnet.config\-Datei für jeden Anwendungspool konfigurieren.  Dies ermöglicht eine Anpassung der Leistung für die einzelnen Anwendungspools.  
  
 Die Standardeinstellung für `maxConcurrentRequestsPerCPU` in [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] ist "5000". Dadurch wird die von ASP.NET gesteuerte Drosselung von Anforderungen deaktiviert, wenn Sie nicht mehr als 5000 Anforderungen pro CPU verwenden.  Die Standardeinstellung verwendet stattdessen den CLR\-Threadpool zur automatischen Verwaltung der Parallelität für die einzelnen CPUs.  Anwendungen, die umfangreichen Gebrauch von asynchroner Anforderungsverarbeitung machen oder zahlreiche Langzeitanforderungen aufweisen, die in Netzwerk\-E\/A blockiert werden, profitieren von der erweiterten Standardgrenze in [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  Wenn Sie `maxConcurrentRequestsPerCPU` auf 0 \(null\) festlegen, wird die Verwendung von verwalteten Threads zur Verarbeitung von ASP.NET\-Anforderungen deaktiviert.  Wenn eine Anwendung in einem IIS\-Anwendungspool ausgeführt wird, verbleiben Anforderungen im E\/A\-Thread von IIS, sodass die Parallelität durch die IIS\-Threadeinstellungen gedrosselt wird.  
  
 Die `requestQueueLimit`\-Einstellung funktioniert analog zum `requestQueueLimit`\-Attribut des [processModel](http://msdn.microsoft.com/de-de/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d)\-Elements, das für ASP.NET\-Anwendungen in Web.config\-Dateien festgelegt wird.  Die `requestQueueLimit`\-Einstellung in einer aspnet.config\-Datei überschreibt jedoch die `requestQueueLimit`\-Einstellung in einer Web.config\-Datei.  Wenn beide Attribute festgelegt werden \(Standardeinstellung\), hat also die `requestQueueLimit`\-Einstellung in der aspnet.config\-Datei Vorrang.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie prozessweites Verhalten von ASP.NET in der aspnet.config\-Datei für folgendes Szenario konfiguriert wird:  
  
-   Die Anwendung wird in einem [!INCLUDE[iisver](../../../../../includes/iisver-md.md)]\-Anwendungspool gehostet.  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] wird im integrierten Modus ausgeführt.  
  
-   Die Anwendung verwendet [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] oder eine höhere Version.  
  
 Die Werte, die im Beispiel verwendet werden, sind Standardwerte.  
  
```  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## Elementinformationen  
  
|||  
|-|-|  
|Namespace||  
|Schemaname||  
|Validierungsdatei||  
|Kann leer sein||  
  
## Siehe auch  
 [\<system.web\>\-Element \(Webeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)