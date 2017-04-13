---
title: "&#196;nderungen zur Laufzeit im .NET Framework 4.5.1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anwendungskompatibilität"
  - "Änderungen zur Laufzeit"
  - ".NET Framework 4.5.1"
ms.assetid: da880ad7-ba0a-4368-b340-705e3533c351
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# &#196;nderungen zur Laufzeit im .NET Framework 4.5.1
In seltenen Fällen können sich Laufzeitänderungen auf Apps auswirken, die auf [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] oder 4.5 abzielen, aber in der 4.51-Laufzeit ausgeführt werden. Dazu zählen Änderungen in folgenden Bereichen:  
  
-   [Core](#Core)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
 Die Spalte "Umfang" in den folgenden Tabellen gibt den Schweregrad der einzelnen Änderungen an:  
  
-   Schwerwiegend. Eine wesentliche Änderung, die viele Apps beeinflusst oder erhebliche Änderungen des Codes erforderlich macht. Beachten Sie, dass keine der Laufzeitänderungen in diese Kategorie fallen.  
  
-   Gering. Eine Änderung, die entweder eine kleine Anzahl von Apps beeinflusst oder geringfügige Änderungen des Codes erforderlich macht.  
  
-   Grenzfall. Eine Änderung, die nur Apps in sehr spezifischen Szenarien beeinflusst, die nicht üblich sind.  
  
-   Transparent. Eine Änderung, die keine nennenswerten Auswirkungen hat, die Entwickler oder Benutzer beachten müssten. Die App sollte keine Änderung benötigen.  
  
<a name="Core"></a>   
## <a name="core-runtime-changes"></a>Laufzeitänderungen im Kern  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> Serialisierung</TKey, TValue>|Ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602> Objekt serialisiert wird in .NET Framework 4.5 mit den <xref:System.Runtime.Serialization.NetDataContractSerializer> kann nicht nur aufgrund von internen Änderungen in den Typ in .NET Framework 4.5.1 und 4.5.2 deserialisiert werden.\</TKey, TValue><br /><br /> Diese Änderung wird *nicht* anwenden, die in den folgenden Szenarien:<br /><br /> Ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602> Objekt in .NET Framework 4.5 serialisiert und deserialisiert Sie der [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].</TKey, TValue> Die <xref:System.Runtime.Serialization.NetDataContractSerializer> in der [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] wird das Objekt zu deserialisieren.<br /><br /> Ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602> Objekt in einer späteren Version von .NET Framework serialisiert und deserialisiert Sie in .NET Framework 4.5.\</TKey, TValue> Die <xref:System.Runtime.Serialization.NetDataContractSerializer> in .NET Framework 4.5 ist das Objekt zu deserialisieren.<br /><br /> Kommunikation zwischen Version Serialisierung und Deserialisierung von einem <xref:System.Collections.Concurrent.ConcurrentDictionary%602> Objekt zwischen jeder beliebigen Version von .NET Framework nach .NET Framework 4.5.</TKey, TValue> Diese Änderung gilt für Objekte, die mit .NET Framework 4.5 serialisiert *nur*.|Zwei problemumgehungen sind verfügbar, wenn serialisieren muss ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602> -Objekt, auf .NET Framework 4.5 und Deserialisieren Sie ihn auf eine höhere Version von .NET Framework:\</TKey, TValue><br /><br /> Verwenden Sie ein alternatives Serialisierungsprogramm, z. B. die <xref:System.Runtime.Serialization.DataContractSerializer> oder <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.<br /><br /> Aktualisieren Sie auf die [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], die Deserialisierung unterstützt <xref:System.Collections.Concurrent.ConcurrentDictionary%602> Objekt serialisiert wird mit .NET Framework 4.5.\</TKey, TValue>|Nebenversion|  
|<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> Klasse|<xref:System.Diagnostics.Tracing.EventListener> schneidet Zeichenfolgen mit eingebetteten NULL-Werte ab. NULL-Zeichen werden nicht unterstützt, indem Sie die <xref:System.Diagnostics.Tracing.EventSource> Klasse.|Die Änderung betrifft nur apps, die <xref:System.Diagnostics.Tracing.EventListener> lesen <xref:System.Diagnostics.Tracing.EventSource> verwenden Sie-Daten im Prozess und die Null-Zeichen als Trennzeichen.|Kante|  
|<xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> Klasse|Die Laufzeit erzwingt jetzt den Vertrag, der Folgendes angibt: eine abgeleitete Klasse <xref:System.Diagnostics.Tracing.EventSource> , definiert eine-ETW-Ereignismethode muss der Basisklasse aufrufen <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=fullName> -Methode mit der Ereignis-ID gefolgt von den gleichen Argumenten, die die ETW-Ereignismethode übergeben wurde.|Ein <xref:System.IndexOutOfRangeException> Ausnahme wird ausgelöst, wenn ein <xref:System.Diagnostics.Tracing.EventListener> liest <xref:System.Diagnostics.Tracing.EventSource> -Daten im Prozess für eine Ereignisquelle, die gegen diesen Vertrag verstößt.<br /><br /> Finden Sie unter [Minderung: EventSource.WriteEvent-Methodenaufrufe](../../../docs/framework/migration-guide/mitigation-eventsource-writeevent-method-calls.md)|Nebenversion|  
|Deserialisierung von Objekten über Anwendungsdomänen hinweg|In einigen Fällen, in denen eine App zwei oder mehr App-Domänen mit unterschiedlichen Anwendungsbasen verwendet, löst der Versuch, Objekte im logischen Aufrufkontext über App-Domänen hinweg zu deserialisieren, eine Ausnahme aus.|Dieses Problem tritt in einem sehr spezifischen Szenario auf. Weitere Informationen und Lösung finden Sie unter [Minderung: Deserialisierung von Objekten über Anwendungsdomänen](../../../docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md).|Kante|  
|<xref:System.IO.Stream.Dispose%2A?displayProperty=fullName> Methode|In [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)] -apps [!INCLUDE[wrt](../../../includes/wrt-md.md)] streamadapter nicht mehr Aufrufen der <xref:System.IO.Stream.FlushAsync%2A> Methode aus der <xref:System.IO.Stream.Dispose%2A> Methode.|Diese Änderung sollte transparent sein. Entwickler können das vorherige Verhalten wiederherstellen, indem sie Code wie den folgenden schreiben:<br /><br /> `using (System.IO.Stream stream = GetWindowsRuntimeStream() As Stream)  {     // do something     await stream.FlushAsync();   }`|Transparent|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf-runtime-changes"></a>Windows Communication Foundation (WCF)-Laufzeitänderungen  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|[MinFreeMemoryPercentageToActiveService](http://msdn.microsoft.com/library/ms731336.aspx) Konfigurationseinstellung|Die Einstellung gibt den minimalen Arbeitsspeicher an, der auf dem Server verfügbar sein muss, bevor ein WCF-Dienst aktiviert werden kann. Es wurde entwickelt, um zu verhindern, dass <xref:System.OutOfMemoryException> Ausnahmen. In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] hatte diese Einstellung keine Auswirkungen. In [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] wird diese Einstellung berücksichtigt.|Eine Ausnahme tritt auf, wenn der auf dem Webserver verfügbare freie Arbeitsspeicher kleiner ist als der Prozentsatz, der in der Konfigurationseinstellung definiert ist. Einige WCF-Dienste, die zuvor erfolgreich in Umgebungen mit eingeschränktem Arbeitsspeicher gestartet und ausgeführt wurden, schlagen jetzt möglicherweise fehl.<br /><br /> Finden Sie unter [Minderung: MinFreeMemoryPercentageToActiveService-Konfigurationseinstellung](../../../docs/framework/migration-guide/mitigation-minfreememorypercentagetoactiveservice-configuration-setting.md).|Nebenversion|  
  
## <a name="see-also"></a>Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-1.md)   
 [Anwendungskompatibilität in 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Anwendungskompatibilität in 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)