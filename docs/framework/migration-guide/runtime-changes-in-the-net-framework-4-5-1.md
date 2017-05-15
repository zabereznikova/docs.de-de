---
title: "Laufzeitänderungen in .NET Framework 4.5.1 | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- runtime changes
- .NET Framework 4.5.1
ms.assetid: da880ad7-ba0a-4368-b340-705e3533c351
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4e4903c2f25354005f95b3ed8f9728cfe8a0a92e
ms.contentlocale: de-de
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-451"></a>Änderungen zur Laufzeit im .NET Framework 4.5.1
In seltenen Fällen können sich Laufzeitänderungen auf Apps auswirken, die auf [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] oder 4.5 abzielen, aber in der 4.51-Laufzeit ausgeführt werden. Dazu zählen Änderungen in folgenden Bereichen:  
  
-   [Kernspeicher](#Core)  
  
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
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>-Serialisierung|Ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602>-Objekt, das in .NET Framework 4.5 mit <xref:System.Runtime.Serialization.NetDataContractSerializer> serialisiert wird, kann in .NET Framework 4.5.1 und 4.5.2 nur aufgrund interner Änderungen am Typ nicht deserialisiert werden.<br /><br /> Diese Änderung gilt *nicht* in folgenden Szenarien:<br /><br /> Ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602>-Objekt, das in .NET Framework 4.5 serialisiert und in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] deserialisiert wurde. Das Objekt kann von <xref:System.Runtime.Serialization.NetDataContractSerializer> in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] deserialisiert werden.<br /><br /> Ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602>-Objekt, das in einer höheren Version von .NET Framework serialisiert und in .NET Framework 4.5 deserialisiert wurde. Das Objekt kann von <xref:System.Runtime.Serialization.NetDataContractSerializer> in .NET Framework 4.5 deserialisiert werden.<br /><br /> Versionsübergreifende Serialisierung und Deserialisierung eines <xref:System.Collections.Concurrent.ConcurrentDictionary%602>-Objekts zwischen beliebigen .NET Framework-Versionen nach .NET Framework 4.5. Diese Änderung gilt *nur* für Objekte, die mit .NET Framework 4.5 serialisiert wurden.|Wenn es erforderlich ist, ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602>-Objekt in .NET Framework 4.5 zu serialisieren und in einer höheren .NET Framework-Version zu deserialisieren, sind zwei Problemumgehungen verfügbar:<br /><br /> Verwenden Sie ein alternatives Serialisierungsprogramm wie <xref:System.Runtime.Serialization.DataContractSerializer> oder <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.<br /><br /> Ein Upgrade für [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], das die Deserialisierung von <xref:System.Collections.Concurrent.ConcurrentDictionary%602>-Objekten unterstützt, die mit .NET Framework 4.5 serialisiert wurden.|Nebenversion|  
|<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName>-Klasse|<xref:System.Diagnostics.Tracing.EventListener> kürzt Zeichenfolgen mit eingebetteten Nullen. NULL-Zeichen werden von der <xref:System.Diagnostics.Tracing.EventSource>-Klasse nicht unterstützt.|Diese Änderung betrifft nur Apps, die <xref:System.Diagnostics.Tracing.EventListener> zum Lesen von verarbeiteten <xref:System.Diagnostics.Tracing.EventSource>-Daten und NULL-Zeichen als Trennzeichen verwenden.|Kante|  
|<xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>-Klasse|Die Laufzeit erzwingt jetzt den Vertrag, der Folgendes angibt: Eine Klasse, die von <xref:System.Diagnostics.Tracing.EventSource> abgeleitet wird und eine ETW-Ereignismethode definiert, muss die <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=fullName>-Methode der Basisklasse mit der Ereignis-ID, gefolgt von den gleichen Argumenten, die an die ETW-Ereignismethode übergeben wurden, aufrufen.|Es wird eine <xref:System.IndexOutOfRangeException>-Ausnahme ausgelöst, wenn ein <xref:System.Diagnostics.Tracing.EventListener> in Verarbeitung befindliche <xref:System.Diagnostics.Tracing.EventSource>-Daten für eine Ereignisquelle liest, die gegen diesen Vertrag verstößt.<br /><br /> Siehe [Entschärfung: EventSource.WriteEvent-Methodenaufrufe](../../../docs/framework/migration-guide/mitigation-eventsource-writeevent-method-calls.md).|Nebenversion|  
|Deserialisierung von Objekten über Anwendungsdomänen hinweg|In einigen Fällen, in denen eine App zwei oder mehr App-Domänen mit unterschiedlichen Anwendungsbasen verwendet, löst der Versuch, Objekte im logischen Aufrufkontext über App-Domänen hinweg zu deserialisieren, eine Ausnahme aus.|Dieses Problem tritt in einem sehr spezifischen Szenario auf. Weitere Informationen und eine Problemumgehung finden Sie unter [Entschärfung: Deserialisierung von Objekten über Anwendungsdomänen](../../../docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md).|Kante|  
|<xref:System.IO.Stream.Dispose%2A?displayProperty=fullName>-Methode|In [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)]-Apps rufen [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Datenstromadapter die <xref:System.IO.Stream.FlushAsync%2A>-Methode nicht länger über die <xref:System.IO.Stream.Dispose%2A>-Methode auf.|Diese Änderung sollte transparent sein. Entwickler können das vorherige Verhalten wiederherstellen, indem sie Code wie den folgenden schreiben:<br /><br /> `using (System.IO.Stream stream = GetWindowsRuntimeStream() As Stream)  {     // do something     await stream.FlushAsync();   }`|Transparent|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf-runtime-changes"></a>Windows Communication Foundation (WCF)-Laufzeitänderungen  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|[minFreeMemoryPercentageToActiveService](http://msdn.microsoft.com/library/ms731336.aspx)-Konfigurationseinstellung|Die Einstellung gibt den minimalen Arbeitsspeicher an, der auf dem Server verfügbar sein muss, bevor ein WCF-Dienst aktiviert werden kann. Sie ist dafür vorgesehen, <xref:System.OutOfMemoryException>-Ausnahmen zu verhindern. In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] hatte diese Einstellung keine Auswirkungen. In [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] wird diese Einstellung berücksichtigt.|Eine Ausnahme tritt auf, wenn der auf dem Webserver verfügbare freie Arbeitsspeicher kleiner ist als der Prozentsatz, der in der Konfigurationseinstellung definiert ist. Einige WCF-Dienste, die zuvor erfolgreich in Umgebungen mit eingeschränktem Arbeitsspeicher gestartet und ausgeführt wurden, schlagen jetzt möglicherweise fehl.<br /><br /> Siehe [Entschärfung: minFreeMemoryPercentageToActiveService-Konfigurationseinstellung](../../../docs/framework/migration-guide/mitigation-minfreememorypercentagetoactiveservice-configuration-setting.md).|Nebenversion|  
  
## <a name="see-also"></a>Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-1.md)   
 [Anwendungskompatibilität in 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Anwendungskompatibilität in 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)
