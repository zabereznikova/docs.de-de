---
title: ETW-Threadpoolereignisse
description: Überprüfen Sie die ETW-Ereignisse des Thread Pools, die Informationen zu Threads in .net sammeln. Thread Pool Ereignisse sind Arbeits Thread Pool-Ereignisse oder e/a-Thread Pool Ereignisse.
ms.date: 03/30/2017
helpviewer_keywords:
- thread pool events [.NET Framework]
- ETW, thread pool events (CLR)
ms.assetid: f2a21e3a-3b6c-4433-97f3-47ff16855ecc
ms.openlocfilehash: 8b00c20e82ee1b1efa6a8a123e66a4cfc239143b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236168"
---
# <a name="thread-pool-etw-events"></a>ETW-Threadpoolereignisse

Diese Ereignisse sammeln Informationen zu Arbeits- und E/A-Threads.  
  
 Es gibt zwei Gruppen von Threadpoolereignissen:  
  
- [Arbeitsthreadpoolereignisse](#worker-thread-pool-events), die Aufschluss darüber geben, wie eine Anwendung den Threadpool verwendet und welchen Effekt Arbeitsauslastungen auf die Parallelitätssteuerung haben.  
  
- [E/A-Threadpoolereignisse](#io-thread-events), die Aufschluss über E/A-Threads geben, die im Threadpool erstellt, deaktiviert, erneut aktiviert oder beendet werden.  

## <a name="worker-thread-pool-events"></a>Arbeitsthreadpoolereignisse

 Diese Ereignisse beziehen sich auf den Arbeitsthreadpool der Laufzeit und stellen Benachrichtigungen für Threadereignisse bereit (wenn z. B. ein Thread erstellt oder beendet wird). Der Arbeitsthreadpool verwendet einen adaptiven Algorithmus für die Parallelitätssteuerung, bei dem die Anzahl der Threads auf Basis des gemessenen Durchsatzes berechnet wird. Arbeitsthreadpoolereignisse können dazu verwendet werden zu verstehen, wie eine Anwendung den Threadpool verwendet und welche Auswirkungen bestimmte Arbeitsauslastungen möglicherweise auf die Parallelitätssteuerung haben.  
  
### <a name="threadpoolworkerthreadstart-and-threadpoolworkerthreadstop"></a>ThreadPoolWorkerThreadStart und ThreadPoolWorkerThreadStop  

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene für diese Ereignisse an. (Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-|-|-|  
|`ThreadPoolWorkerThreadStart`|50|Ein Arbeitsthread wird erstellt.|  
|`ThreadPoolWorkerThreadStop`|51|Ein Arbeitsthread wird beendet.|  
|`ThreadPoolWorkerThreadRetirementStart`|52|Ein Arbeitsthread wird deaktiviert.|  
|`ThreadPoolWorkerThreadRetirementStop`|53|Ein deaktivierter Arbeitsthread wird wieder aktiviert.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|BESCHREIBUNG|  
|----------------|---------------|-----------------|  
|ActiveWorkerThreadCount|win:UInt32|Die Anzahl der Arbeitsthreads, die zum Verarbeiten der Arbeitsvorgänge verfügbar sind, einschließlich der Threads, die bereits Arbeitsvorgänge verarbeiten.|  
|RetiredWorkerThreadCount|win:UInt32|Die Anzahl der Arbeitsthreads, die nicht zum Verarbeiten von Arbeitsvorgängen verfügbar sind, die aber für den Fall als Reserve vorgehalten werden, dass später weitere Threads benötigt werden.|  
|ClrInstanceID|Win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
### <a name="threadpoolworkerthreadadjustment"></a>ThreadPoolWorkerThreadAdjustment  

 Diese Threadpoolereignisse bieten Informationen, um das Verhalten des Algorithmus zur Threadinjektion (Parallelitätssteuerung) zu verstehen und zu debuggen. Die Informationen werden intern vom Arbeitsthreadpool verwendet.  
  
#### <a name="threadpoolworkerthreadadjustmentsample"></a>ThreadPoolWorkerThreadAdjustmentSample  

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|BESCHREIBUNG|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentSample`|54|Bezieht sich auf die Auflistung von Informationen für ein Beispiel, d. h. eine Messung des Durchsatzes mit einer bestimmten Parallelitätsebene zu einem bestimmten Zeitpunkt.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|BESCHREIBUNG|  
|----------------|---------------|-----------------|  
|Throughput|win:Double|Anzahl von Abschlüssen pro Zeiteinheit.|  
|ClrInstanceID|Win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
#### <a name="threadpoolworkerthreadadjustmentadjustment"></a>ThreadPoolWorkerThreadAdjustmentAdjustment  

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|BESCHREIBUNG|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|55|Zeichnet eine Änderung der Steuerung auf, wenn der Algorithmus zur Threadinjektion (Hill-Climbing) ermittelt, dass auf der Parallelitätsebene eine Änderung vorgenommen wird.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|BESCHREIBUNG|  
|----------------|---------------|-----------------|  
|AverageThroughput|win:Double|Durchschnittlicher Durchsatz für eine Stichprobe von Messungen.|  
|NewWorkerThreadCount|win:UInt32|Neue Anzahl aktiver Arbeitsthreads.|  
|`Reason`|win:UInt32|Grund für die Anpassung.<br /><br /> 0x00 – Aufwärmphase.<br /><br /> 0x01 – Initialisierung.<br /><br /> 0x02 - Zufällige Verschiebung.<br /><br /> 0x03 – Steigende Verschiebung.<br /><br /> 0x04 – Änderungspunkt.<br /><br /> 0x05 – Stabilisierung.<br /><br /> 0x06 – Außerkraftsetzung.<br /><br /> 0x07 – Zeitlimit für Thread überschritten.|  
|ClrInstanceID|Win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
#### <a name="threadpoolworkerthreadadjustmentstats"></a>ThreadPoolWorkerThreadAdjustmentStats  

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|BESCHREIBUNG|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentStats`|56|Erfasst Daten zum Threadpool.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|BESCHREIBUNG|  
|----------------|---------------|-----------------|  
|Duration|win:Double|Zeitdauer in Sekunden, in der diese statistischen Daten erfasst wurden.|  
|Throughput|win:Double|Durchschnittliche Anzahl von Abschlüssen pro Sekunde während dieses Intervalls.|  
|ThreadWave|win:Double|Für die interne Verwendung reserviert.|  
|ThroughputWave|win:Double|Für die interne Verwendung reserviert.|  
|ThroughputErrorEstimate|win:Double|Für die interne Verwendung reserviert.|  
|AverageThroughputErrorEstimate|win:Double|Für die interne Verwendung reserviert.|  
|ThroughputRatio|win:Double|Die relative Verbesserung beim Durchsatz, die durch Abweichungen bei der aktiven Arbeitsthreadanzahl während dieses Intervalls verursacht wurde.|  
|Confidence|win:Double|Ein Maß für die Gültigkeit des „ThroughputRatio“-Felds.|  
|NewcontrolSetting|win:Double|Die Anzahl der aktiven Arbeitsthreads, die als Grundlage für zukünftige Abweichungen bei der Anzahl aktiver Threads dienen werden.|  
|NewThreadWaveMagnitude|Win:UInt16|Das Ausmaß zukünftiger Abweichungen bei der Anzahl aktiver Threads.|  
|ClrInstanceID|Win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  

## <a name="io-thread-events"></a>E/A-Threadereignisse  

 Diese Threadpoolereignisse treten für Threads im E/A-Threadpool (Abschlussanschluss) auf, der asynchron ist.  
  
### <a name="iothreadcreate_v1"></a>IOThreadCreate_V1  

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-|-|-|  
|`IOThreadCreate_V1`|44|Ein E/A-Thread wird im Threadpool erstellt.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|BESCHREIBUNG|  
|----------------|---------------|-----------------|  
|Anzahl|win:UInt64|Anzahl der E/A-Threads, einschließlich des neu erstellten Threads.|  
|NumRetired|win:UInt64|Anzahl deaktivierter Arbeitsthreads.|  
|ClrInstanceID|Win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
### <a name="iothreadretire_v1"></a>IOThreadRetire_V1  

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`IOThreadRetire_V1`|46|Ein E/A-Thread wird zum Kandidaten für die Deaktivierung.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|BESCHREIBUNG|  
|----------------|---------------|-----------------|  
|Anzahl|win:UInt64|Anzahl der im Threadpool verbleibenden E/A-Threads.|  
|NumRetired|win:UInt64|Anzahl deaktivierter E/A-Threads.|  
|ClrInstanceID|Win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
### <a name="iothreadunretire_v1"></a>IOThreadUnretire_V1  

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`IOThreadUnretire_V1`|47|Ein E/A-Threads wird aufgrund von E/A-Vorgängen erneut aktiviert, die während einer Wartefrist auftreten, nachdem der Thread zum Kandidaten für die Deaktivierung geworden ist.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|BESCHREIBUNG|  
|----------------|---------------|-----------------|  
|Anzahl|win:UInt64|Anzahl der E/A-Threads im Threadpool, einschließlich dieses Threads.|  
|NumRetired|win:UInt64|Anzahl deaktivierter E/A-Threads.|  
|ClrInstanceID|Win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
### <a name="iothreadterminate"></a>IOThreadTerminate  

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`IOThreadTerminate`|45|Ein e/a-Thread wird im Thread Pool beendet.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|BESCHREIBUNG|  
|----------------|---------------|-----------------|  
|Anzahl|win:UInt64|Anzahl der im Threadpool verbleibenden E/A-Threads.|  
|NumRetired|win:UInt64|Anzahl deaktivierter E/A-Threads.|  
|ClrInstanceID|Win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
## <a name="see-also"></a>Weitere Informationen

- [CLR-ETW-Ereignisse](clr-etw-events.md)
