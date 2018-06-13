---
title: WCF-Leistungsindikatoren
ms.date: 03/30/2017
helpviewer_keywords:
- performance counters [WCF]
ms.assetid: f559b2bd-ed83-4988-97a1-e88f06646609
ms.openlocfilehash: 1d9e6b83a78967193c4cb0343f6c77560354a837
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33805167"
---
# <a name="wcf-performance-counters"></a><span data-ttu-id="08cf0-102">WCF-Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="08cf0-102">WCF Performance Counters</span></span>
<span data-ttu-id="08cf0-103">Windows Communication Foundation (WCF) enthält eine Reihe von Leistungsindikatoren zur Messung der Leistung Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="08cf0-103">Windows Communication Foundation (WCF) includes a large set of performance counters to help you gauge your application's performance.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="08cf0-104">Aktivieren von Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="08cf0-104">Enabling Performance Counters</span></span>  
 <span data-ttu-id="08cf0-105">Sie können die Leistungsindikatoren für einen WCF-Dienst über die Konfigurationsdatei "App.config" des WCF-Diensts wie folgt aktivieren:</span><span class="sxs-lookup"><span data-stu-id="08cf0-105">You can enable performance counters for a WCF service through the app.config configuration file of the WCF service as follows:</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <diagnostics performanceCounters="All" />  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="08cf0-106">Das `performanceCounters`-Attribut kann dafür festgelegt werden, dass ein bestimmter Typ von Leistungsindikatoren aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="08cf0-106">The `performanceCounters` attribute can be set to enable a specific type of performance counters.</span></span> <span data-ttu-id="08cf0-107">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="08cf0-107">Valid values are</span></span>  
  
-   <span data-ttu-id="08cf0-108">All: Alle Kategorieindikatoren (ServiceModelService, ServiceModelEndpoint und ServiceModelOperation) werden aktiviert.</span><span class="sxs-lookup"><span data-stu-id="08cf0-108">All: All category counters (ServiceModelService, ServiceModelEndpoint and ServiceModelOperation) are enabled.</span></span>  
  
-   <span data-ttu-id="08cf0-109">ServiceOnly: Nur ServiceModelService-Kategorieindikatoren werden aktiviert.</span><span class="sxs-lookup"><span data-stu-id="08cf0-109">ServiceOnly: Only ServiceModelService category counters are enabled.</span></span> <span data-ttu-id="08cf0-110">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="08cf0-110">This is the default value.</span></span>  
  
-   <span data-ttu-id="08cf0-111">Off: ServiceModel\*-Leistungsindikatoren werden deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="08cf0-111">Off: ServiceModel\* performance counters are disabled.</span></span>  
  
 <span data-ttu-id="08cf0-112">Wenn Sie die Leistungsindikatoren für alle WCF-Anwendungen aktivieren möchten, können Sie die Konfigurationseinstellungen in der Datei "Machine.config" platzieren.</span><span class="sxs-lookup"><span data-stu-id="08cf0-112">If you want to enable performance counters for all WCF applications, you can place the configuration settings in the Machine.config file.</span></span>  <span data-ttu-id="08cf0-113">Finden Sie unter der **Erhöhen der Arbeitsspeichergröße für Leistungsindikatoren** weiter unten für Weitere Informationen zum Konfigurieren ausreichenden Arbeitsspeichers für Leistungsindikatoren auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="08cf0-113">Please see the **Increasing Memory Size for Performance Counters** section below for more information on configuring sufficient memory for performance counters on your machine.</span></span>  
  
 <span data-ttu-id="08cf0-114">Bei Verwendung von WCF-Erweiterbarkeitspunkte wie benutzerdefinierte Vorgänge Aufrufern vorgesehen, sollten Sie auch eigene Leistungsindikatoren ausgeben.</span><span class="sxs-lookup"><span data-stu-id="08cf0-114">If you use WCF extensibility points such as custom operation invokers, you should also emit your own performance counters.</span></span> <span data-ttu-id="08cf0-115">Dies liegt daran, wenn Sie einen Erweiterungspunkt implementieren, WCF nicht mehr die Standardleistungsindikatoren im Standardpfad ausgeben kann.</span><span class="sxs-lookup"><span data-stu-id="08cf0-115">This is because if you implement an extensibility point, WCF may no longer emit the standard performance counter data in the default path.</span></span> <span data-ttu-id="08cf0-116">Wenn Sie keine Unterstützung für manuelle Leistungsindikatoren implementieren, werden die erwarteten Leistungsindikatordaten möglicherweise nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08cf0-116">If you do not implement manual performance counter support, you may not see the performance counter data you expect.</span></span>  
  
 <span data-ttu-id="08cf0-117">Leistungsindikatoren können auch folgendermaßen im Code aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="08cf0-117">You can also enable performance counters in your code as follows,</span></span>  
  
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
  
## <a name="viewing-performance-data"></a><span data-ttu-id="08cf0-118">Anzeigen von Leistungsdaten</span><span class="sxs-lookup"><span data-stu-id="08cf0-118">Viewing Performance Data</span></span>  
 <span data-ttu-id="08cf0-119">Wenn Sie von den Leistungsindikatoren erfasste Daten anzeigen möchten, verwenden Sie den in Windows integrierten Leistungsmonitor (Perfmon.exe).</span><span class="sxs-lookup"><span data-stu-id="08cf0-119">To view data captured by the performance counters, you can use the Performance Monitor (Perfmon.exe) that comes with Windows.</span></span> <span data-ttu-id="08cf0-120">Sie können dieses Tool starten, navigieren Sie zu **starten**, und klicken Sie auf **ausführen** und Typ `perfmon.exe` im Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="08cf0-120">You can launch this tool by going to **Start**, and click **Run** and type `perfmon.exe` in the dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08cf0-121">Leistungsindikatorinstanzen werden möglicherweise freigegeben, bevor die letzten Nachrichten vom Endpunktverteiler verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="08cf0-121">Performance counter instances may be released before the last messages have been processed by the endpoint dispatcher.</span></span> <span data-ttu-id="08cf0-122">Dies kann dazu führen, dass Leistungsdaten für einige Nachrichten nicht erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="08cf0-122">This can result in performance data not being captured for a few messages.</span></span>  
  
## <a name="increasing-memory-size-for-performance-counters"></a><span data-ttu-id="08cf0-123">Erhöhen der Arbeitsspeichergröße für Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="08cf0-123">Increasing Memory Size for Performance Counters</span></span>  
 <span data-ttu-id="08cf0-124">WCF wird separaten freigegebenen Arbeitsspeicher für die Leistungsindikatorkategorien verwendet.</span><span class="sxs-lookup"><span data-stu-id="08cf0-124">WCF uses separate shared memory for its performance counter categories.</span></span>  
  
 <span data-ttu-id="08cf0-125">Standardmäßig wird separater freigegebener Arbeitsspeicher auf ein Viertel der Größe des globalen Leistungsindikator-Arbeitsspeichers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="08cf0-125">By default, separate shared memory is set to a quarter the size of global performance counter memory.</span></span> <span data-ttu-id="08cf0-126">Der standardmäßige globale Leistungsindikator-Arbeitsspeicher besitzt eine Größe von 524.288 Byte.</span><span class="sxs-lookup"><span data-stu-id="08cf0-126">The default global performance counter memory is 524,288 bytes.</span></span> <span data-ttu-id="08cf0-127">Daher müssen die drei WCF-Leistungsindikatorkategorien eine Standardgröße von ungefähr 128KB.</span><span class="sxs-lookup"><span data-stu-id="08cf0-127">Therefore, the three WCF performance counter categories have a default size of approximately 128KB each.</span></span> <span data-ttu-id="08cf0-128">Abhängig von den laufzeitmerkmalen der WCF-Anwendungen auf einem Computer, kann Arbeitsspeicher des Leistungsindikators erschöpft.</span><span class="sxs-lookup"><span data-stu-id="08cf0-128">Depending upon the runtime characteristics of the WCF applications on a machine, performance counter memory may be exhausted.</span></span> <span data-ttu-id="08cf0-129">In diesem Fall schreibt WCF einen Fehler in das Anwendungsereignisprotokoll auf.</span><span class="sxs-lookup"><span data-stu-id="08cf0-129">When this happens, WCF writes an error to the application event log.</span></span> <span data-ttu-id="08cf0-130">Der Inhaltsfehler gibt an, dass ein Leistungsindikator nicht geladen wurde, und der Eintrag beinhaltet die Ausnahme "System.InvalidOperationException: Nicht genügend Arbeitsspeicher zum Anzeigen der benutzerdefinierten Indikatordatei."</span><span class="sxs-lookup"><span data-stu-id="08cf0-130">The content of the error states that a performance counter was not loaded, and the entry contains the exception "System.InvalidOperationException: Custom counters file view is out of memory."</span></span> <span data-ttu-id="08cf0-131">Wird die Ablaufverfolgung auf Fehlerebene aktiviert, wird dieser Fehler ebenfalls nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="08cf0-131">If tracing is enabled at the error level, this failure is also traced.</span></span> <span data-ttu-id="08cf0-132">Wenn der Arbeitsspeicher des Leistungsindikators erschöpft ist, kann zur Ausführung der WCF-Anwendung mit aktivierten Leistungsindikatoren zu fortfahren zu Leistungseinbußen führen.</span><span class="sxs-lookup"><span data-stu-id="08cf0-132">If performance counter memory is exhausted, continuing to run your WCF applications with performance counters enabled could result in performance degradation.</span></span> <span data-ttu-id="08cf0-133">Der zuständige Administrator sollte den Computer für das Zuordnen von ausreichendem Arbeitsspeicher konfigurieren, damit die maximale Anzahl der Leistungsindikatoren, die jederzeit vorhanden sein können, unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="08cf0-133">If you are an administrator of the machine, you should configure it to allocate enough memory to support the maximum number of performance counters that can exist at any time.</span></span>  
  
 <span data-ttu-id="08cf0-134">Sie können die Menge des Leistungsindikator-Arbeitsspeichers für WCF-Kategorien in der Registrierung ändern.</span><span class="sxs-lookup"><span data-stu-id="08cf0-134">You can change the amount of performance counter memory for WCF categories in the registry.</span></span> <span data-ttu-id="08cf0-135">Dazu muss den drei folgenden Speicherorten ein neuer DWORD-Wert mit der Bezeichnung `FileMappingSize` hinzugefügt und auf den gewünschten Wert in Byte festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="08cf0-135">To do so, you need to add a new DWORD value named `FileMappingSize` to the three following locations, and set it to the desired value in bytes.</span></span> <span data-ttu-id="08cf0-136">Starten Sie den Computer neu, damit diese Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="08cf0-136">Reboot your machine so that these changes are taken into effect.</span></span>  
  
-   <span data-ttu-id="08cf0-137">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="08cf0-137">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span></span>  
  
-   <span data-ttu-id="08cf0-138">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="08cf0-138">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span></span>  
  
-   <span data-ttu-id="08cf0-139">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="08cf0-139">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span></span>  
  
 <span data-ttu-id="08cf0-140">Wenn eine große Anzahl von Objekten (z. B. ServiceHost) verworfen wird, die automatische Speicherbereinigung jedoch noch aussteht, registriert der `PrivateBytes`-Leistungsindikator eine ungewöhnlich hohe Anzahl.</span><span class="sxs-lookup"><span data-stu-id="08cf0-140">When a large number of objects (for example, ServiceHost) are disposed of but waiting to be garbage-collected, the `PrivateBytes` performance counter will register an unusually high number.</span></span> <span data-ttu-id="08cf0-141">Zum Beheben dieses Problems können Sie entweder eigene anwendungsspezifische Indikatoren hinzufügen oder mithilfe des `performanceCounters`-Attributs nur Indikatoren auf Dienstebene aktivieren.</span><span class="sxs-lookup"><span data-stu-id="08cf0-141">To resolve this problem, you can either add your own application-specific counters, or use the `performanceCounters` attribute to enable only service-level counters.</span></span>  
  
## <a name="types-of-performance-counters"></a><span data-ttu-id="08cf0-142">Leistungsindikatortypen</span><span class="sxs-lookup"><span data-stu-id="08cf0-142">Types of Performance Counters</span></span>  
 <span data-ttu-id="08cf0-143">Leistungsindikatoren werden für drei verschiedene Ebenen festgelegt: Dienst, Endpunkt und Vorgang.</span><span class="sxs-lookup"><span data-stu-id="08cf0-143">Performance counters are scoped to three different levels: Service, Endpoint and Operation.</span></span>  
  
 <span data-ttu-id="08cf0-144">Sie können WMI verwenden, um den Namen einer Leistungsindikatorinstanz abzurufen.</span><span class="sxs-lookup"><span data-stu-id="08cf0-144">You can use WMI to retrieve the name of a performance counter instance.</span></span> <span data-ttu-id="08cf0-145">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="08cf0-145">For example,</span></span>  
  
-   <span data-ttu-id="08cf0-146">-Instanzname Service abgerufen werden kann, über WMI [Service](../../../../../docs/framework/wcf/diagnostics/wmi/service.md) -Instanz "CounterInstanceName"-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="08cf0-146">Service counter instance name can be obtained through WMI [Service](../../../../../docs/framework/wcf/diagnostics/wmi/service.md) instance's "CounterInstanceName" property.</span></span>  
  
-   <span data-ttu-id="08cf0-147">-Instanzname Endpunkt abgerufen werden kann, über WMI [Endpunkt](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) -Instanz "CounterInstanceName"-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="08cf0-147">Endpoint counter instance name can be obtained through WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) instance's "CounterInstanceName" property.</span></span>  
  
-   <span data-ttu-id="08cf0-148">-Instanzname Vorgang abgerufen werden kann, über WMI [Endpunkt](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) -Instanz "GetOperationCounterInstanceName"-Methode.</span><span class="sxs-lookup"><span data-stu-id="08cf0-148">Operation counter instance name can be obtained through WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) instance's "GetOperationCounterInstanceName" method.</span></span>  
  
 <span data-ttu-id="08cf0-149">Weitere Informationen zu WMI finden Sie unter [mithilfe von Windows-Verwaltungsinstrumentation für die Diagnose](../../../../../docs/framework/wcf/diagnostics/wmi/index.md).</span><span class="sxs-lookup"><span data-stu-id="08cf0-149">For more information on WMI, see [Using Windows Management Instrumentation for Diagnostics](../../../../../docs/framework/wcf/diagnostics/wmi/index.md).</span></span>  
  
### <a name="service-performance-counters"></a><span data-ttu-id="08cf0-150">Dienstleistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="08cf0-150">Service performance counters</span></span>  
 <span data-ttu-id="08cf0-151">Mit Dienst-Leistungsindikatoren wird das Dienstverhalten insgesamt gemessen und die Leistung des gesamten Diensts geprüft.</span><span class="sxs-lookup"><span data-stu-id="08cf0-151">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="08cf0-152">Sie sind beim Anzeigen mit dem Leistungsmonitor unter dem `ServiceModelService 4.0.0.0`-Leistungsobjekt zu finden.</span><span class="sxs-lookup"><span data-stu-id="08cf0-152">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="08cf0-153">Die Instanzen werden nach dem folgenden Schema benannt:</span><span class="sxs-lookup"><span data-stu-id="08cf0-153">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
 <span data-ttu-id="08cf0-154">Ein Indikator in einem Dienstbereich wird vom Indikator in einer Auflistung von Endpunkten aggregiert.</span><span class="sxs-lookup"><span data-stu-id="08cf0-154">A counter in a service scope is aggregated from counter in a collection of endpoints.</span></span>  
  
 <span data-ttu-id="08cf0-155">Leistungsindikatoren zur Dienstinstanzerstellung werden inkrementiert, wenn ein neuer InstanceContext erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="08cf0-155">Performance counters for service instance creation are incremented when a new InstanceContext is created.</span></span> <span data-ttu-id="08cf0-156">Beachten Sie, dass auch dann ein neuer InstanceContext erstellt wird, wenn eine nicht aktivierende Nachricht empfangen wird (mit einem vorhandenen Dienst), oder wenn Sie von einer Sitzung aus eine Verbindung zu einer Instanz herstellen, die Sitzung beenden und dann von einer anderen Sitzung aus die Verbindung wieder herstellen.</span><span class="sxs-lookup"><span data-stu-id="08cf0-156">Note that a new InstanceContext is created even when you receive a non-activating message (with an existing service), or when you connect to an instance from one session, end the session, and then reconnect from another session.</span></span>  
  
### <a name="endpoint-performance-counters"></a><span data-ttu-id="08cf0-157">Endpunktleistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="08cf0-157">Endpoint performance counters</span></span>  
 <span data-ttu-id="08cf0-158">Endpunktleistungsindikatoren ermöglichen das Anzeigen von Daten, die das Akzeptieren von Nachrichten durch einen Endpunkt widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="08cf0-158">Endpoint performance counters enable you to look at data reflecting how an endpoint is accepting messages.</span></span> <span data-ttu-id="08cf0-159">Sie sind beim Anzeigen mit dem Leistungsmonitor unter dem `ServiceModelEndpoint 4.0.0.0`-Leistungsobjekt zu finden.</span><span class="sxs-lookup"><span data-stu-id="08cf0-159">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing using the Performance Monitor.</span></span> <span data-ttu-id="08cf0-160">Die Instanzen werden nach dem folgenden Schema benannt:</span><span class="sxs-lookup"><span data-stu-id="08cf0-160">The instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="08cf0-161">Die Daten ähneln den Daten, die für einzelne Vorgänge erfasst werden, sie werden jedoch nur über den Endpunkt aggregiert.</span><span class="sxs-lookup"><span data-stu-id="08cf0-161">The data is similar to what is collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
 <span data-ttu-id="08cf0-162">Ein Indikator in einem Endpunktbereich wird von den Indikatoren in einer Auflistung von Vorgängen aggregiert.</span><span class="sxs-lookup"><span data-stu-id="08cf0-162">A counter in an endpoint scope is aggregated from counters in a collection of operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08cf0-163">Wenn zwei Endpunkte identische Vertragsnamen und Adressen besitzen, werden sie derselben Indikatorinstanz zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="08cf0-163">If two endpoints have identical contract names and addresses, they are mapped to the same counter instance.</span></span>  
  
### <a name="operation-performance-counters"></a><span data-ttu-id="08cf0-164">Vorgangsleistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="08cf0-164">Operation performance counters</span></span>  
 <span data-ttu-id="08cf0-165">Vorgangsleistungsindikatoren befinden sich unter dem `ServiceModelOperation 4.0.0.0`-Leistungsobjekt, wenn sie mit dem Leistungsmonitor angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="08cf0-165">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="08cf0-166">Jeder Vorgang hat eine einzelne Instanz.</span><span class="sxs-lookup"><span data-stu-id="08cf0-166">Each operation has an individual instance.</span></span> <span data-ttu-id="08cf0-167">Das heißt, wenn ein bestimmter Vertrag 10 Vorgänge enthält, werden mit diesem Vertrag 10 Vorgangsleistungsindikatoren verbunden.</span><span class="sxs-lookup"><span data-stu-id="08cf0-167">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="08cf0-168">Die Objektinstanzen werden nach dem folgenden Muster benannt:</span><span class="sxs-lookup"><span data-stu-id="08cf0-168">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="08cf0-169">Mit diesem Indikator können Sie messen, wie der Aufruf verwendet wird und wie gut der Vorgang funktioniert.</span><span class="sxs-lookup"><span data-stu-id="08cf0-169">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
 <span data-ttu-id="08cf0-170">Wenn Indikatoren in mehreren Bereichen angezeigt werden können, werden von einem höheren Bereich gesammelte Daten mit Daten aus niedrigeren Bereichen aggregiert.</span><span class="sxs-lookup"><span data-stu-id="08cf0-170">When counters are visible at multiple scopes, data gathered from a higher scope are aggregated with data from lower scopes.</span></span> <span data-ttu-id="08cf0-171">Beispielsweise ist `Calls` an einem Endpunkt die Summe aller Vorgangsaufrufe innerhalb des Endpunkts; bei einem Dienst ist `Calls` die Summe aller Aufrufe von Endpunkten innerhalb des Diensts.</span><span class="sxs-lookup"><span data-stu-id="08cf0-171">For example, `Calls` at an endpoint represents the sum of all operation calls within the endpoint; `Calls` at a service represents the sum of all calls to all endpoints within the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08cf0-172">Sind in einem Vertrag Vorgangsnamen doppelt vorhanden, wird nur eine Indikatorinstanz für beide Vorgänge ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="08cf0-172">If you have duplicate operation names on a contract, you only get one counter instances for both operations.</span></span>  
  
## <a name="programming-the-wcf-performance-counters"></a><span data-ttu-id="08cf0-173">Programmieren der WCF-Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="08cf0-173">Programming the WCF Performance Counters</span></span>  
 <span data-ttu-id="08cf0-174">Mehrere Dateien im SDK-Installationsordner installiert, sodass Sie die WCF-Leistungsindikatoren programmgesteuert zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="08cf0-174">Several files are installed in the SDK install folder so that you can access the WCF performance counters programmatically.</span></span> <span data-ttu-id="08cf0-175">Diese Dateien werden wie folgt aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="08cf0-175">These files are listed as follows.</span></span>  
  
-   <span data-ttu-id="08cf0-176">_ServiceModelEndpointPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="08cf0-176">_ServiceModelEndpointPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="08cf0-177">_ServiceModelOperationPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="08cf0-177">_ServiceModelOperationPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="08cf0-178">_ServiceModelServicePerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="08cf0-178">_ServiceModelServicePerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="08cf0-179">_SMSvcHostPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="08cf0-179">_SMSvcHostPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="08cf0-180">_TransactionBridgePerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="08cf0-180">_TransactionBridgePerfCounters.vrg</span></span>  
  
 <span data-ttu-id="08cf0-181">Weitere Informationen zum Leistungsindikatoren programmgesteuert zugreifen, finden Sie unter [Architektur der Leistungsindikatorprogrammierung](http://go.microsoft.com/fwlink/?LinkId=95179).</span><span class="sxs-lookup"><span data-stu-id="08cf0-181">For more information on how to access the counters programmatically, see [Performance Counter Programming Architecture](http://go.microsoft.com/fwlink/?LinkId=95179).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08cf0-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08cf0-182">See Also</span></span>  
 [<span data-ttu-id="08cf0-183">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="08cf0-183">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
