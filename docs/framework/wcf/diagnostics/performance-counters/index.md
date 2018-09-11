---
title: WCF-Leistungsindikatoren
ms.date: 03/30/2017
helpviewer_keywords:
- performance counters [WCF]
ms.assetid: f559b2bd-ed83-4988-97a1-e88f06646609
ms.openlocfilehash: d0ad7ee0bc3ea1d15197e6b8d9888d60b21a2f15
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275301"
---
# <a name="wcf-performance-counters"></a><span data-ttu-id="a5625-102">WCF-Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="a5625-102">WCF Performance Counters</span></span>
<span data-ttu-id="a5625-103">Windows Communication Foundation (WCF) umfasst eine große Anzahl von Leistungsindikatoren können Sie die Leistung Ihrer Anwendung zu messen.</span><span class="sxs-lookup"><span data-stu-id="a5625-103">Windows Communication Foundation (WCF) includes a large set of performance counters to help you gauge your application's performance.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="a5625-104">Aktivieren von Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="a5625-104">Enabling Performance Counters</span></span>  
 <span data-ttu-id="a5625-105">Sie können die Leistungsindikatoren für einen WCF-Dienst über die Konfigurationsdatei "App.config" des WCF-Diensts wie folgt aktivieren:</span><span class="sxs-lookup"><span data-stu-id="a5625-105">You can enable performance counters for a WCF service through the app.config configuration file of the WCF service as follows:</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <diagnostics performanceCounters="All" />  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="a5625-106">Das `performanceCounters`-Attribut kann dafür festgelegt werden, dass ein bestimmter Typ von Leistungsindikatoren aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="a5625-106">The `performanceCounters` attribute can be set to enable a specific type of performance counters.</span></span> <span data-ttu-id="a5625-107">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="a5625-107">Valid values are</span></span>  
  
-   <span data-ttu-id="a5625-108">All: Alle Kategorieindikatoren (ServiceModelService, ServiceModelEndpoint und ServiceModelOperation) werden aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a5625-108">All: All category counters (ServiceModelService, ServiceModelEndpoint and ServiceModelOperation) are enabled.</span></span>  
  
-   <span data-ttu-id="a5625-109">ServiceOnly: Nur ServiceModelService-Kategorieindikatoren werden aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a5625-109">ServiceOnly: Only ServiceModelService category counters are enabled.</span></span> <span data-ttu-id="a5625-110">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="a5625-110">This is the default value.</span></span>  
  
-   <span data-ttu-id="a5625-111">Off: ServiceModel\*-Leistungsindikatoren werden deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a5625-111">Off: ServiceModel\* performance counters are disabled.</span></span>  
  
 <span data-ttu-id="a5625-112">Wenn Sie die Leistungsindikatoren für alle WCF-Anwendungen aktivieren möchten, können Sie die Konfigurationseinstellungen in der Datei "Machine.config" platzieren.</span><span class="sxs-lookup"><span data-stu-id="a5625-112">If you want to enable performance counters for all WCF applications, you can place the configuration settings in the Machine.config file.</span></span>  <span data-ttu-id="a5625-113">Informieren Sie sich die **Erhöhen der Arbeitsspeichergröße für Leistungsindikatoren** Abschnitt unten für Weitere Informationen zum Konfigurieren ausreichenden Arbeitsspeichers für Leistungsindikatoren auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="a5625-113">Please see the **Increasing Memory Size for Performance Counters** section below for more information on configuring sufficient memory for performance counters on your machine.</span></span>  
  
 <span data-ttu-id="a5625-114">Wenn Sie WCF-Erweiterbarkeitspunkte wie z. B. benutzerdefinierte Vorgangsaufrufer verwenden, sollten Sie auch eigene Leistungsindikatoren ausgeben.</span><span class="sxs-lookup"><span data-stu-id="a5625-114">If you use WCF extensibility points such as custom operation invokers, you should also emit your own performance counters.</span></span> <span data-ttu-id="a5625-115">Das liegt bei der Implementierung eines Erweiterungspunkts WCF nicht mehr die standardmäßigen Leistungsindikatordaten im Standardpfad ausgeben kann.</span><span class="sxs-lookup"><span data-stu-id="a5625-115">This is because if you implement an extensibility point, WCF may no longer emit the standard performance counter data in the default path.</span></span> <span data-ttu-id="a5625-116">Wenn Sie keine Unterstützung für manuelle Leistungsindikatoren implementieren, werden die erwarteten Leistungsindikatordaten möglicherweise nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5625-116">If you do not implement manual performance counter support, you may not see the performance counter data you expect.</span></span>  
  
 <span data-ttu-id="a5625-117">Leistungsindikatoren können auch folgendermaßen im Code aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="a5625-117">You can also enable performance counters in your code as follows,</span></span>  
  
```  
using System.Configuration;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Diagnostics;  
Configuration config = ConfigurationManager.OpenExeConfiguration(  
    ConfigurationUserLevel.None);  
ServiceModelSectionGroup sg = ServiceModelSectionGroup.GetSectionGroup(config);  
sg.Diagnostic.PerformanceCounters = PerformanceCounterScope.All;  
config.Save();  
```  
  
## <a name="viewing-performance-data"></a><span data-ttu-id="a5625-118">Anzeigen von Leistungsdaten</span><span class="sxs-lookup"><span data-stu-id="a5625-118">Viewing Performance Data</span></span>  
 <span data-ttu-id="a5625-119">Wenn Sie von den Leistungsindikatoren erfasste Daten anzeigen möchten, verwenden Sie den in Windows integrierten Leistungsmonitor (Perfmon.exe).</span><span class="sxs-lookup"><span data-stu-id="a5625-119">To view data captured by the performance counters, you can use the Performance Monitor (Perfmon.exe) that comes with Windows.</span></span> <span data-ttu-id="a5625-120">Sie können dieses Tool starten, indem Sie zu **starten**, und klicken Sie auf **ausführen** und `perfmon.exe` im Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="a5625-120">You can launch this tool by going to **Start**, and click **Run** and type `perfmon.exe` in the dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5625-121">Leistungsindikatorinstanzen werden möglicherweise freigegeben, bevor die letzten Nachrichten vom Endpunktverteiler verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="a5625-121">Performance counter instances may be released before the last messages have been processed by the endpoint dispatcher.</span></span> <span data-ttu-id="a5625-122">Dies kann dazu führen, dass Leistungsdaten für einige Nachrichten nicht erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="a5625-122">This can result in performance data not being captured for a few messages.</span></span>  
  
## <a name="increasing-memory-size-for-performance-counters"></a><span data-ttu-id="a5625-123">Erhöhen der Arbeitsspeichergröße für Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="a5625-123">Increasing Memory Size for Performance Counters</span></span>  
 <span data-ttu-id="a5625-124">WCF verwendet separaten freigegebenen Arbeitsspeicher für die Leistungsindikatorkategorien.</span><span class="sxs-lookup"><span data-stu-id="a5625-124">WCF uses separate shared memory for its performance counter categories.</span></span>  
  
 <span data-ttu-id="a5625-125">Standardmäßig wird separater freigegebener Arbeitsspeicher auf ein Viertel der Größe des globalen Leistungsindikator-Arbeitsspeichers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a5625-125">By default, separate shared memory is set to a quarter the size of global performance counter memory.</span></span> <span data-ttu-id="a5625-126">Der standardmäßige globale Leistungsindikator-Arbeitsspeicher besitzt eine Größe von 524.288 Byte.</span><span class="sxs-lookup"><span data-stu-id="a5625-126">The default global performance counter memory is 524,288 bytes.</span></span> <span data-ttu-id="a5625-127">Daher müssen die drei WCF-Leistungsindikatorkategorien eine Standardgröße von ungefähr 128KB.</span><span class="sxs-lookup"><span data-stu-id="a5625-127">Therefore, the three WCF performance counter categories have a default size of approximately 128KB each.</span></span> <span data-ttu-id="a5625-128">Abhängig von den laufzeitmerkmalen der WCF-Clientanwendungen auf einem Computer, kann Arbeitsspeicher des Leistungsindikators erschöpft sein.</span><span class="sxs-lookup"><span data-stu-id="a5625-128">Depending upon the runtime characteristics of the WCF applications on a machine, performance counter memory may be exhausted.</span></span> <span data-ttu-id="a5625-129">In diesem Fall schreibt WCF einen Fehler in das Anwendungsereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="a5625-129">When this happens, WCF writes an error to the application event log.</span></span> <span data-ttu-id="a5625-130">Der Inhaltsfehler gibt an, dass ein Leistungsindikator nicht geladen wurde, und der Eintrag beinhaltet die Ausnahme "System.InvalidOperationException: Nicht genügend Arbeitsspeicher zum Anzeigen der benutzerdefinierten Indikatordatei."</span><span class="sxs-lookup"><span data-stu-id="a5625-130">The content of the error states that a performance counter was not loaded, and the entry contains the exception "System.InvalidOperationException: Custom counters file view is out of memory."</span></span> <span data-ttu-id="a5625-131">Wird die Ablaufverfolgung auf Fehlerebene aktiviert, wird dieser Fehler ebenfalls nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="a5625-131">If tracing is enabled at the error level, this failure is also traced.</span></span> <span data-ttu-id="a5625-132">Wenn der Arbeitsspeicher des Leistungsindikators erschöpft ist, kann weiterhin ausgeführt wird Ihre WCF-Anwendungen mit aktivierten Leistungsindikatoren zu Leistungseinbußen führen.</span><span class="sxs-lookup"><span data-stu-id="a5625-132">If performance counter memory is exhausted, continuing to run your WCF applications with performance counters enabled could result in performance degradation.</span></span> <span data-ttu-id="a5625-133">Der zuständige Administrator sollte den Computer für das Zuordnen von ausreichendem Arbeitsspeicher konfigurieren, damit die maximale Anzahl der Leistungsindikatoren, die jederzeit vorhanden sein können, unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a5625-133">If you are an administrator of the machine, you should configure it to allocate enough memory to support the maximum number of performance counters that can exist at any time.</span></span>  
  
 <span data-ttu-id="a5625-134">Sie können die Menge des Leistungsindikator-Arbeitsspeichers für WCF-Kategorien in der Registrierung ändern.</span><span class="sxs-lookup"><span data-stu-id="a5625-134">You can change the amount of performance counter memory for WCF categories in the registry.</span></span> <span data-ttu-id="a5625-135">Dazu muss den drei folgenden Speicherorten ein neuer DWORD-Wert mit der Bezeichnung `FileMappingSize` hinzugefügt und auf den gewünschten Wert in Byte festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="a5625-135">To do so, you need to add a new DWORD value named `FileMappingSize` to the three following locations, and set it to the desired value in bytes.</span></span> <span data-ttu-id="a5625-136">Starten Sie den Computer neu, damit diese Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="a5625-136">Reboot your machine so that these changes are taken into effect.</span></span>  
  
-   <span data-ttu-id="a5625-137">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="a5625-137">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span></span>  
  
-   <span data-ttu-id="a5625-138">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="a5625-138">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span></span>  
  
-   <span data-ttu-id="a5625-139">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="a5625-139">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span></span>  
  
 <span data-ttu-id="a5625-140">Wenn eine große Anzahl von Objekten (z. B. ServiceHost) verworfen wird, die automatische Speicherbereinigung jedoch noch aussteht, registriert der `PrivateBytes`-Leistungsindikator eine ungewöhnlich hohe Anzahl.</span><span class="sxs-lookup"><span data-stu-id="a5625-140">When a large number of objects (for example, ServiceHost) are disposed of but waiting to be garbage-collected, the `PrivateBytes` performance counter will register an unusually high number.</span></span> <span data-ttu-id="a5625-141">Zum Beheben dieses Problems können Sie entweder eigene anwendungsspezifische Indikatoren hinzufügen oder mithilfe des `performanceCounters`-Attributs nur Indikatoren auf Dienstebene aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a5625-141">To resolve this problem, you can either add your own application-specific counters, or use the `performanceCounters` attribute to enable only service-level counters.</span></span>  
  
## <a name="types-of-performance-counters"></a><span data-ttu-id="a5625-142">Leistungsindikatortypen</span><span class="sxs-lookup"><span data-stu-id="a5625-142">Types of Performance Counters</span></span>  
 <span data-ttu-id="a5625-143">Leistungsindikatoren werden für drei verschiedene Ebenen festgelegt: Dienst, Endpunkt und Vorgang.</span><span class="sxs-lookup"><span data-stu-id="a5625-143">Performance counters are scoped to three different levels: Service, Endpoint and Operation.</span></span>  
  
 <span data-ttu-id="a5625-144">Sie können WMI verwenden, um den Namen einer Leistungsindikatorinstanz abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a5625-144">You can use WMI to retrieve the name of a performance counter instance.</span></span> <span data-ttu-id="a5625-145">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a5625-145">For example,</span></span>  
  
-   <span data-ttu-id="a5625-146">-Instanzname des Indikators Service erhalten Sie über WMI [Service](../../../../../docs/framework/wcf/diagnostics/wmi/service.md) die "CounterInstanceName"-Eigenschaft der Instanz.</span><span class="sxs-lookup"><span data-stu-id="a5625-146">Service counter instance name can be obtained through WMI [Service](../../../../../docs/framework/wcf/diagnostics/wmi/service.md) instance's "CounterInstanceName" property.</span></span>  
  
-   <span data-ttu-id="a5625-147">Namen der Leistungsindikatorinstanz Endpunkt erhalten Sie über WMI [Endpunkt](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) die "CounterInstanceName"-Eigenschaft der Instanz.</span><span class="sxs-lookup"><span data-stu-id="a5625-147">Endpoint counter instance name can be obtained through WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) instance's "CounterInstanceName" property.</span></span>  
  
-   <span data-ttu-id="a5625-148">Namen der Leistungsindikatorinstanz Vorgang erhalten Sie über WMI [Endpunkt](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) die "GetOperationCounterInstanceName"-Methode Instanz.</span><span class="sxs-lookup"><span data-stu-id="a5625-148">Operation counter instance name can be obtained through WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) instance's "GetOperationCounterInstanceName" method.</span></span>  
  
 <span data-ttu-id="a5625-149">Weitere Informationen zu WMI finden Sie unter [mithilfe von Windows-Verwaltungsinstrumentation für die Diagnose](../../../../../docs/framework/wcf/diagnostics/wmi/index.md).</span><span class="sxs-lookup"><span data-stu-id="a5625-149">For more information on WMI, see [Using Windows Management Instrumentation for Diagnostics](../../../../../docs/framework/wcf/diagnostics/wmi/index.md).</span></span>  
  
### <a name="service-performance-counters"></a><span data-ttu-id="a5625-150">Dienstleistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="a5625-150">Service performance counters</span></span>  
 <span data-ttu-id="a5625-151">Mit Dienst-Leistungsindikatoren wird das Dienstverhalten insgesamt gemessen und die Leistung des gesamten Diensts geprüft.</span><span class="sxs-lookup"><span data-stu-id="a5625-151">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="a5625-152">Sie sind beim Anzeigen mit dem Leistungsmonitor unter dem `ServiceModelService 4.0.0.0`-Leistungsobjekt zu finden.</span><span class="sxs-lookup"><span data-stu-id="a5625-152">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="a5625-153">Die Instanzen werden nach dem folgenden Schema benannt:</span><span class="sxs-lookup"><span data-stu-id="a5625-153">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
 <span data-ttu-id="a5625-154">Ein Indikator in einem Dienstbereich wird vom Indikator in einer Auflistung von Endpunkten aggregiert.</span><span class="sxs-lookup"><span data-stu-id="a5625-154">A counter in a service scope is aggregated from counter in a collection of endpoints.</span></span>  
  
 <span data-ttu-id="a5625-155">Leistungsindikatoren zur Dienstinstanzerstellung werden inkrementiert, wenn ein neuer InstanceContext erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a5625-155">Performance counters for service instance creation are incremented when a new InstanceContext is created.</span></span> <span data-ttu-id="a5625-156">Beachten Sie, dass auch dann ein neuer InstanceContext erstellt wird, wenn eine nicht aktivierende Nachricht empfangen wird (mit einem vorhandenen Dienst), oder wenn Sie von einer Sitzung aus eine Verbindung zu einer Instanz herstellen, die Sitzung beenden und dann von einer anderen Sitzung aus die Verbindung wieder herstellen.</span><span class="sxs-lookup"><span data-stu-id="a5625-156">Note that a new InstanceContext is created even when you receive a non-activating message (with an existing service), or when you connect to an instance from one session, end the session, and then reconnect from another session.</span></span>  
  
### <a name="endpoint-performance-counters"></a><span data-ttu-id="a5625-157">Endpunktleistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="a5625-157">Endpoint performance counters</span></span>  
 <span data-ttu-id="a5625-158">Endpunktleistungsindikatoren ermöglichen das Anzeigen von Daten, die das Akzeptieren von Nachrichten durch einen Endpunkt widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="a5625-158">Endpoint performance counters enable you to look at data reflecting how an endpoint is accepting messages.</span></span> <span data-ttu-id="a5625-159">Sie sind beim Anzeigen mit dem Leistungsmonitor unter dem `ServiceModelEndpoint 4.0.0.0`-Leistungsobjekt zu finden.</span><span class="sxs-lookup"><span data-stu-id="a5625-159">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing using the Performance Monitor.</span></span> <span data-ttu-id="a5625-160">Die Instanzen werden nach dem folgenden Schema benannt:</span><span class="sxs-lookup"><span data-stu-id="a5625-160">The instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="a5625-161">Die Daten ähneln den Daten, die für einzelne Vorgänge erfasst werden, sie werden jedoch nur über den Endpunkt aggregiert.</span><span class="sxs-lookup"><span data-stu-id="a5625-161">The data is similar to what is collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
 <span data-ttu-id="a5625-162">Ein Indikator in einem Endpunktbereich wird von den Indikatoren in einer Auflistung von Vorgängen aggregiert.</span><span class="sxs-lookup"><span data-stu-id="a5625-162">A counter in an endpoint scope is aggregated from counters in a collection of operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5625-163">Wenn zwei Endpunkte identische Vertragsnamen und Adressen besitzen, werden sie derselben Indikatorinstanz zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a5625-163">If two endpoints have identical contract names and addresses, they are mapped to the same counter instance.</span></span>  
  
### <a name="operation-performance-counters"></a><span data-ttu-id="a5625-164">Vorgangsleistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="a5625-164">Operation performance counters</span></span>  
 <span data-ttu-id="a5625-165">Vorgangsleistungsindikatoren befinden sich unter dem `ServiceModelOperation 4.0.0.0`-Leistungsobjekt, wenn sie mit dem Leistungsmonitor angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a5625-165">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="a5625-166">Jeder Vorgang hat eine einzelne Instanz.</span><span class="sxs-lookup"><span data-stu-id="a5625-166">Each operation has an individual instance.</span></span> <span data-ttu-id="a5625-167">Das heißt, wenn ein bestimmter Vertrag 10 Vorgänge enthält, werden mit diesem Vertrag 10 Vorgangsleistungsindikatoren verbunden.</span><span class="sxs-lookup"><span data-stu-id="a5625-167">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="a5625-168">Die Objektinstanzen werden nach dem folgenden Muster benannt:</span><span class="sxs-lookup"><span data-stu-id="a5625-168">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="a5625-169">Mit diesem Indikator können Sie messen, wie der Aufruf verwendet wird und wie gut der Vorgang funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a5625-169">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
 <span data-ttu-id="a5625-170">Wenn Indikatoren in mehreren Bereichen angezeigt werden können, werden von einem höheren Bereich gesammelte Daten mit Daten aus niedrigeren Bereichen aggregiert.</span><span class="sxs-lookup"><span data-stu-id="a5625-170">When counters are visible at multiple scopes, data gathered from a higher scope are aggregated with data from lower scopes.</span></span> <span data-ttu-id="a5625-171">Beispielsweise ist `Calls` an einem Endpunkt die Summe aller Vorgangsaufrufe innerhalb des Endpunkts; bei einem Dienst ist `Calls` die Summe aller Aufrufe von Endpunkten innerhalb des Diensts.</span><span class="sxs-lookup"><span data-stu-id="a5625-171">For example, `Calls` at an endpoint represents the sum of all operation calls within the endpoint; `Calls` at a service represents the sum of all calls to all endpoints within the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5625-172">Sind in einem Vertrag Vorgangsnamen doppelt vorhanden, wird nur eine Indikatorinstanz für beide Vorgänge ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="a5625-172">If you have duplicate operation names on a contract, you only get one counter instances for both operations.</span></span>  
  
## <a name="programming-the-wcf-performance-counters"></a><span data-ttu-id="a5625-173">Programmieren der WCF-Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="a5625-173">Programming the WCF Performance Counters</span></span>  
 <span data-ttu-id="a5625-174">Mehrere Dateien werden in SDK-Installationsordner installiert, sodass Sie die WCF-Leistungsindikatoren programmgesteuert zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="a5625-174">Several files are installed in the SDK install folder so that you can access the WCF performance counters programmatically.</span></span> <span data-ttu-id="a5625-175">Diese Dateien werden wie folgt aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="a5625-175">These files are listed as follows.</span></span>  
  
-   <span data-ttu-id="a5625-176">_ServiceModelEndpointPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="a5625-176">_ServiceModelEndpointPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="a5625-177">_ServiceModelOperationPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="a5625-177">_ServiceModelOperationPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="a5625-178">_ServiceModelServicePerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="a5625-178">_ServiceModelServicePerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="a5625-179">_SMSvcHostPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="a5625-179">_SMSvcHostPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="a5625-180">_TransactionBridgePerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="a5625-180">_TransactionBridgePerfCounters.vrg</span></span>  
  
 <span data-ttu-id="a5625-181">Weitere Informationen zum programmgesteuerten Zugriff auf die Indikatoren finden Sie unter [Architektur der Leistungsindikatorprogrammierung](https://go.microsoft.com/fwlink/?LinkId=95179).</span><span class="sxs-lookup"><span data-stu-id="a5625-181">For more information on how to access the counters programmatically, see [Performance Counter Programming Architecture](https://go.microsoft.com/fwlink/?LinkId=95179).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5625-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5625-182">See Also</span></span>  
 [<span data-ttu-id="a5625-183">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="a5625-183">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
