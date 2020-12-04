---
title: Thread Pool-Lauf Zeit Ereignisse
description: Weitere Informationen finden Sie unter .NET-Runtime-Thread Pool Ereignisse, die Diagnoseinformationen zum Thread Pool in .net Core sammeln. Thread Pool Ereignisse sind Arbeits Thread Pool-Ereignisse oder e/a-Thread Pool Ereignisse.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- ThreadPool events (CoreCLR)
- ETW, thread pool events (CoreCLR)
ms.openlocfilehash: cdd6041c5842d4922c60e33daf6db366f7d35327
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96592107"
---
# <a name="net-runtime-thread-pool-events"></a>.NET-Runtime-Thread Pool Ereignisse

Diese Ereignisse sammeln Informationen über Worker-und e/a-Threads im Thread Pool. Weitere Informationen zur Verwendung dieser Ereignisse zu Diagnose Zwecken finden Sie unter [Protokollierung und Ablauf Verfolgung von .NET-Anwendungen](../../core/diagnostics/logging-tracing.md) .

## <a name="iothreadcreate_v1-event"></a>IOThreadCreate_V1 Ereignis

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Information (4)|

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------------------------------|-----------|
|`IOThreadCreate_V1`|44|Ein E/A-Thread wird im Threadpool erstellt.|

 Die folgende Tabelle zeigt die Ereignisdaten an.

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|Anzahl der E/A-Threads, einschließlich des neu erstellten Threads.|
|`NumRetired`|`win:UInt64`|Anzahl deaktivierter Arbeitsthreads.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="iothreadterminate_v1-event"></a>IOThreadTerminate_V1 Ereignis

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene
|-----------------------------------|-----------
|`ThreadingKeyword` (0x10000)|Information (4)

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`IOThreadTerminate`|45|Ein e/a-Thread wird im Thread Pool beendet.|

 Die folgende Tabelle zeigt die Ereignisdaten an.

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|Anzahl der im Threadpool verbleibenden E/A-Threads.|
|`NumRetired`|`win:UInt64`|Anzahl deaktivierter E/A-Threads.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="iothreadretire_v1-event"></a>IOThreadRetire_V1 Ereignis

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
|`Count`|`win:UInt64`|Anzahl der im Threadpool verbleibenden E/A-Threads.|
|`NumRetired`|`win:UInt64`|Anzahl deaktivierter E/A-Threads.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="iothreadunretire_v1-event"></a>IOThreadUnretire_V1 Ereignis

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
|`Count`|`win:UInt64`|Anzahl der E/A-Threads im Threadpool, einschließlich dieses Threads.|
|`NumRetired`|`win:UInt64`|Anzahl deaktivierter E/A-Threads.|
|`ClrInstanceID`|`Win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="threadpoolworkerthreadstart-event"></a>Threadpoolworkerthreadstart-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStart`|50|Ein Arbeitsthread wird erstellt.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|Die Anzahl der Arbeitsthreads, die zum Verarbeiten der Arbeitsvorgänge verfügbar sind, einschließlich der Threads, die bereits Arbeitsvorgänge verarbeiten.|
|`RetiredWorkerThreadCount`|`win:UInt32`|Die Anzahl der Arbeitsthreads, die nicht zum Verarbeiten von Arbeitsvorgängen verfügbar sind, die aber für den Fall als Reserve vorgehalten werden, dass später weitere Threads benötigt werden.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="threadpoolworkerthreadstop-event"></a>Threadpoolworkerthreadstoppt-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStop`|51|Ein Arbeitsthread wird beendet.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|Die Anzahl der Arbeitsthreads, die zum Verarbeiten der Arbeitsvorgänge verfügbar sind, einschließlich der Threads, die bereits Arbeitsvorgänge verarbeiten.|
|`RetiredWorkerThreadCount`|`win:UInt32`|Die Anzahl der Arbeitsthreads, die nicht zum Verarbeiten von Arbeitsvorgängen verfügbar sind, die aber für den Fall als Reserve vorgehalten werden, dass später weitere Threads benötigt werden.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="threadpoolworkerthreadwait-event"></a>Threadpoolworkerthreadwait-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadWait`|57|Ein Arbeits Thread wartet auf die Arbeit.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|Die Anzahl der Arbeitsthreads, die zum Verarbeiten der Arbeitsvorgänge verfügbar sind, einschließlich der Threads, die bereits Arbeitsvorgänge verarbeiten.|
|`RetiredWorkerThreadCount`|`win:UInt32`|Die Anzahl der Arbeitsthreads, die nicht zum Verarbeiten von Arbeitsvorgängen verfügbar sind, die aber für den Fall als Reserve vorgehalten werden, dass später weitere Threads benötigt werden.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="threadpoolworkerthreadretirementstart-event"></a>Threadpoolworkerthreadretirementstart-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStart`|52|Ein Arbeitsthread wird deaktiviert.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|Die Anzahl der Arbeitsthreads, die zum Verarbeiten der Arbeitsvorgänge verfügbar sind, einschließlich der Threads, die bereits Arbeitsvorgänge verarbeiten.|
|`RetiredWorkerThreadCount`|`win:UInt32`|Die Anzahl der Arbeitsthreads, die nicht zum Verarbeiten von Arbeitsvorgängen verfügbar sind, die aber für den Fall als Reserve vorgehalten werden, dass später weitere Threads benötigt werden.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="threadpoolworkerthreadretirementstop-event"></a>Threadpoolworkerthreadretirementend-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStop`|53|Ein deaktivierter Arbeitsthread wird wieder aktiviert.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|Die Anzahl der Arbeitsthreads, die zum Verarbeiten der Arbeitsvorgänge verfügbar sind, einschließlich der Threads, die bereits Arbeitsvorgänge verarbeiten.|
|`RetiredWorkerThreadCount`|`win:UInt32`|Die Anzahl der Arbeitsthreads, die nicht zum Verarbeiten von Arbeitsvorgängen verfügbar sind, die aber für den Fall als Reserve vorgehalten werden, dass später weitere Threads benötigt werden.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="threadpoolworkerthreadadjustmentsample-event"></a>Threadpoolworkerthreadaccessmentsample-Ereignis

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
|`Throughput`|`win:Double`|Anzahl von Abschlüssen pro Zeiteinheit.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="threadpoolworkerthreadadjustmentadjustment-event"></a>Threadpoolworkerthreadanpassmentadjustment-Ereignis

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
|`AverageThroughput`|`win:Double`|Durchschnittlicher Durchsatz für eine Stichprobe von Messungen.|
|`NewWorkerThreadCount`|`win:UInt32`|Neue Anzahl aktiver Arbeitsthreads.|
|`Reason`|`win:UInt32`|Grund für die Anpassung.<br /><br /> `0x0` Aufwärm Dauer.<br /><br /> `0x1` Initialisieren.<br /><br /> `0x2` -Zufällige Verschiebung.<br /><br /> `0x3` -Klettern verschieben.<br /><br /> `0x4` -Punkt ändern.<br /><br /> `0x5` Stabilisierungs.<br /><br /> `0x6` Nöten.<br /><br /> `0x7` -Beim Thread ist ein Timeout aufgetreten.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="threadpoolworkerthreadadjustmentstats-event"></a>Threadpoolworkerthreadaccessmentstats-Ereignis

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Ausführlich (5)

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentStats`|56|Erfasst Daten zum Threadpool.|

 In der folgenden Tabelle werden die Ereignisdaten angezeigt.

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`Duration`|`win:Double`|Zeitdauer in Sekunden, in der diese statistischen Daten erfasst wurden.|
|`Throughput`|`win:Double`|Durchschnittliche Anzahl von Abschlüssen pro Sekunde während dieses Intervalls.|
|`ThreadWave`|`win:Double`|Für die interne Verwendung reserviert.|
|`ThroughputWave`|`win:Double`|Für die interne Verwendung reserviert.|
|`ThroughputErrorEstimate`|`win:Double`|Für die interne Verwendung reserviert.|
|`AverageThroughputErrorEstimate`|`win:Double`|Für die interne Verwendung reserviert.|
|`ThroughputRatio`|`win:Double`|Die relative Verbesserung beim Durchsatz, die durch Abweichungen bei der aktiven Arbeitsthreadanzahl während dieses Intervalls verursacht wurde.|
|`Confidence`|`win:Double`|Ein Maß für die Gültigkeit des „ThroughputRatio“-Felds.|
|`NewcontrolSetting`|`win:Double`|Die Anzahl der aktiven Arbeitsthreads, die als Grundlage für zukünftige Abweichungen bei der Anzahl aktiver Threads dienen werden.|
|`NewThreadWaveMagnitude`|`win:UInt16`|Das Ausmaß zukünftiger Abweichungen bei der Anzahl aktiver Threads.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="threadpoolenqueue-event"></a>Thread pooleinqueue-Ereignis

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Ausführlich (5)

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`ThreadPoolEnqueue`|61|Ein Arbeits Element wurde in die Warteschlange des Thread Pools eingereiht.|

 In der folgenden Tabelle werden die Ereignisdaten angezeigt.

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|Zeiger auf die Arbeits Anforderung.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="threadpooldequeue-event"></a>Threadpoolentqueue-Ereignis

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Ausführlich (5)

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`ThreadPoolDequeue`|62|Eine Arbeitsaufgabe wurde aus der Warteschlange des Thread Pools entfernt.|

 In der folgenden Tabelle werden die Ereignisdaten angezeigt.

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|Zeiger auf die Arbeits Anforderung.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="threadpoolioenqueue-event"></a>Threadpoolioenqueue-Ereignis

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Ausführlich (5)

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`ThreadPoolIOEnqueue`|63|Ein Thread fügt eine e/A-Abschluss Benachrichtigung nach einem asynchronen e/A-Abschluss ein.|

 In der folgenden Tabelle werden die Ereignisdaten angezeigt.

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|Für die interne Verwendung reserviert.|
|`Overlapped`|`win:Pointer`|Für die interne Verwendung reserviert.|
|`MultiDequeues`|`win:Boolean`|Für die interne Verwendung reserviert.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="threadpooliodequeue-event"></a>Threadpooliodequeue-Ereignis

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Ausführlich (5)

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`ThreadPoolIODequeue`|64|Ein Thread entfernt die e/A-Abschluss Benachrichtigung.|

 In der folgenden Tabelle werden die Ereignisdaten angezeigt.

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|Für die interne Verwendung reserviert.|
|`Overlapped`|`win:Pointer`|Für die interne Verwendung reserviert.|
|`MultiDequeues`|`win:Boolean`|Für die interne Verwendung reserviert.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="threadpooliopack-event"></a>Threadpooliopack-Ereignis

 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Ausführlich (5)|

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`ThreadPoolIOPack`|65|Das überlappende Thread Pool-e/a-Paket wird aufgerufen.|

 In der folgenden Tabelle werden die Ereignisdaten angezeigt.

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|Für die interne Verwendung reserviert.|
|`Overlapped`|`win:Pointer`|Für die interne Verwendung reserviert.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="threadcreating-event"></a>Thread Creating-Ereignis

 In der folgenden Tabelle sind die Schlüsselwörter und die Ebene aufgeführt.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Information (4)|

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ThreadCreating`|70|Der Thread wurde erstellt.|

 Die folgende Tabelle zeigt die Ereignisdaten an.

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|Thread-ID|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="threadrunning-event"></a>Thread Running-Ereignis

 In der folgenden Tabelle sind die Schlüsselwörter und die Ebene aufgeführt.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Information (4)|

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ThreadRunning`|71|Die Ausführung des Threads wurde gestartet.|

 Die folgende Tabelle zeigt die Ereignisdaten an.

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|Thread-ID|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|
