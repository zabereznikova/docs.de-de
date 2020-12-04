---
title: Lauf Zeit Ereignisse der Garbage Collection
description: Weitere Informationen zu .NET-Garbage Collector finden Sie unter .net-Lauf Zeit Ereignisse.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- GC events
- garbage collection events (CoreCLR)
- ETW, EventPipe, LTTng garbage collection events (CoreCLR)
ms.openlocfilehash: 2799a93f351baf23ec7a359b0b4b2be5c216dc4d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "96592085"
---
# <a name="net-runtime-garbage-collection-events"></a>Ereignisse der .net-Lauf Zeit Garbage Collection

Diese Ereignisse sammeln Informationen, die die Garbage Collection betreffen. Sie helfen bei der Diagnose und beim Debuggen, einschließlich der Ermittlung, wie oft Garbage Collection ausgeführt wurde, wie viel Arbeitsspeicher während Garbage Collection freigegeben wurde usw. Weitere Informationen zur Verwendung dieser Ereignisse zu Diagnose Zwecken finden Sie unter [Protokollierung und Ablauf Verfolgung von .NET-Anwendungen](../../core/diagnostics/logging-tracing.md) .

## <a name="gcstart_v2-event"></a>GCStart_V2 Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`GCStart_V1`|1|Eine Garbage Collection gestartet wurde.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|Die *N*-te Garbage Collection.|
|`Depth`|`win:UInt32`|Die erfasste Generation.|
|`Reason`|`win:UInt32`|Grund für die Auslösung der Garbage Collection:<br /><br /> `0x0` -Zuordnung für kleinen Objekt Heap.<br /><br /> `0x1` Geführt.<br /><br /> `0x2` -Wenig Arbeitsspeicher.<br /><br /> `0x3` Leer.<br /><br /> `0x4` -Zuordnung für großen Objekt Heap.<br /><br /> `0x5` -Nicht genügend Speicherplatz (für kleinen Objekt Heap).<br /><br /> `0x6` -Nicht genügend Speicherplatz (für großen Objekt Heap).<br /><br /> `0x7` -Induziert, aber nicht als blockierend erzwungen.|
|`Type`|`win:UInt32`|`0x0` -Blockierende Garbage Collection außerhalb der Hintergrund Garbage Collection aufgetreten.<br /><br /> `0x1` -Hintergrund Garbage Collection.<br /><br /> `0x2` -Blockierende Garbage Collection bei Hintergrund Garbage Collection aufgetreten.|
|`ClrInstanceID`|win:UInt16|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="gcend_v1-event"></a>GCEnd_V1-Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`GCEnd_V1`|2|Die Garbage Collection beendet wurde.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|Die *N*-te Garbage Collection.|
|`Depth`|`win:UInt32`|Die Generation, die erfasst wurde.|
|`ClrInstanceID`|win:UInt16|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="gcheapstats_v2-event"></a>GCHeapStats_V2 Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`GCHeapStats_V2`|4|Zeigt die Heapstatistik am Ende jeder Garbage Collection an.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`GenerationSize0`|`win:UInt64`|Die Größe des Arbeitsspeichers der Generation 0 in Bytes.|
|`TotalPromotedSize0`|`win:UInt64`|Die Anzahl der Bytes, die von Generation 0 zu Generation 1 höher gestuft werden.|
|`GenerationSize1`|`win:UInt64`|Die Größe des Arbeitsspeichers der Generation 1 in Bytes.|
|`TotalPromotedSize1`|`win:UInt64`|Die Anzahl der Bytes, die von Generation 1 zu Generation 2 höher gestuft werden.|
|`GenerationSize2`|`win:UInt64`|Die Größe des Arbeitsspeichers der Generation 2 in Bytes.|
|`TotalPromotedSize2`|`win:UInt64`|Die Anzahl der Bytes, die nach der letzten Garbage Collection in Generation 2 noch vorhanden sind.|
|`GenerationSize3`|`win:UInt64`|Die Größe des großen Objektheaps in Bytes.|
|`TotalPromotedSize3`|`win:UInt64`|Die Anzahl der Bytes, die nach der letzten Garbage Collection im großen Objektheap noch vorhanden sind.|
|`FinalizationPromotedSize`|`win:UInt64`|Die Gesamtgröße der Objekte in Bytes, die auf einen Abschluss warten.|
|`FinalizationPromotedCount`|`win:UInt64`|Die Anzahl der Objekte, die auf einen Abschluss warten.|
|`PinnedObjectCount`|`win:UInt32`|Die Anzahl der fixierten (unverschiebbaren) Objekte.|
|`SinkBlockCount`|`win:UInt32`|Die Anzahl der verwendeten Synchronisierungsblöcke.|
|`GCHandleCount`|`win:UInt32`|Die Anzahl der verwendeten Garbage Collection-Handles.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|
|`GenerationSize4`|`win:UInt64`|Die Größe des fixierten Objekt Heaps in Bytes.|
|`TotalPromotedSize4`|`win:UInt64`|Die Anzahl der Bytes, die nach der letzten Auflistung im angehefteten Objekt Heap noch nicht angezeigt wurden.|

## <a name="gccreatesegment_v1-event"></a>GCCreateSegment_V1 Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|5|Neues Garbage Collection-Segment wurde erstellt. Darüber hinaus wird dieses Ereignis für jedes vorhandene Segment ausgelöst, wenn die Ablaufverfolgung für einen Prozess aktiviert ist, der bereits ausgeführt wird.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`Address`|`win:UInt64`|Die Adresse des Segments.|
|`Size`|`win:UInt64`|Die Größe des Segments.|
|`Type`|`win:UInt32`|0x0 – Kleiner Objektheap.<br /><br /> 0x1 – Großer Objektheap.<br /><br /> 0x2 – Schreibgeschützter Heap.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

Beachten Sie, dass die Größe der Segmente, die vom Garbage Collector zugeordnet werden, implementierungsspezifisch ist und jederzeit, auch in regelmäßigen Updates, geändert werden kann. Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen noch darf in ihr versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren.

## <a name="gcfreesegment_v1-event"></a>GCFreeSegment_V1 Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|6|Ein Garbage Collection-Segment freigegeben wurde.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`Address`|`win:UInt64`|Die Adresse des Segments.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="gcrestarteebegin_v1-event"></a>GCRestartEEBegin_V1 Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|7|Die Wiederaufnahme der Common Language Runtime-Unterbrechung begonnen hat.|

Dieses Ereignis weist keine Ereignisdaten auf.

## <a name="gcrestarteeend_v1-event"></a>GCRestartEEEnd_V1 Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|3|Die Wiederaufnahme der Common Language Runtime-Unterbrechung beendet wurde.|

Dieses Ereignis weist keine Ereignisdaten auf.

## <a name="gcsuspendeeend_v1-event"></a>GCSuspendEEEnd_V1 Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|8|Die Unterbrechung der Ausführungs-Engine für die Garbage Collection beendet wurde.|

Dieses Ereignis weist keine Ereignisdaten auf.

## <a name="gcsuspendeebegin_v1-event"></a>GCSuspendEEBegin_V1 Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`GCSuspendEEBegin_V1`|8|Die Unterbrechung der Ausführungs-Engine für die Garbage Collection gestartet wurde.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|Die *N*-te Garbage Collection.|
|`Reason`|`win:UInt32`|Grund für das Anhalten der EE.<br/><br/>`0x0`: Aussetzen für andere<br/><br/>`0x1`: Suspend für GC.<br/><br/>`0x2`: Aussetzen für das Herunterfahren der AppDomain.<br/><br/>`0x3`: Suspend für Code-Pitching.<br/><br/>`0x4`: Suspend für das Herunterfahren.<br/><br/>`0x5`: Suspend für Debugger.<br/><br/>`0x6`: Suspend für GC Prep.<br/><br/>`0x7`: Aussetzen für Debugger-Sweep|

## <a name="gcallocationtick_v3-event"></a>GCAllocationTick_V3 Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Ausführlich (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`GCAllocationTick_V3`|10|Jedes Mal werden ungefähr 100 KB zugeordnet.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`AllocationAmount`|`win:UInt32`|Die Zuordnungsgröße in Bytes. Dieser Wert ist für Zuordnungen präzise, die kleiner als die Länge von ULONG sind (4.294.967.295 Bytes). Wenn die Zuordnung größer ist, enthält dieses Feld einen abgeschnittenen Wert. Verwenden Sie `AllocationAmount64` für sehr große Zuordnungen.|
|`AllocationKind`|`win:UInt32`|`0x0` -Kleine Objekt Zuordnung (Zuordnung erfolgt im kleinen Objekt Heap).<br /><br /> `0x1` -Die Zuordnung von großen Objekten (die Zuordnung erfolgt im großen Objekt Heap).|
|`AllocationAmount64`|`win:UInt64`|Die Zuordnungsgröße in Bytes. Dieser Wert ist für sehr große Zuordnungen präzise.|
|`TypeId`|`win:Pointer`|Die Adresse der Methodentabelle. Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies die Adresse der Methodentabelle, die dem zuletzt zugeordneten Objekt (das Objekt, das den Schwellenwert von 100 KB überschritten hat) entspricht.|
|`TypeName`|`win:UnicodeString`|Der Name des zugeordneten Typs. Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies der Typ des zuletzt zugeordneten Objekts (das Objekt, das den Schwellenwert von 100 KB überschritten hat).|
|`HeapIndex`|`win:UInt32`|Der Heap, auf dem das Objekt zugeordnet wurde. Dieser Wert ist 0 (null), wenn die Ausführung mit Garbage Collection für die Arbeitsstation erfolgt.|
|`Address`|`win:Pointer`|Die Adresse des zuletzt zugeordneten Objekts.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="gccreateconcurrentthread_v1-event"></a>GCCreateConcurrentThread_V1 Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Information (4)|
|`ThreadingKeyword` (0x10000)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|11|Thread für parallele Garbage Collection erstellt wurde.|

Dieses Ereignis weist keine Ereignisdaten auf.

## <a name="gcterminateconcurrentthread_v1-event"></a>GCTerminateConcurrentThread_V1 Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Information (4)|
|`ThreadingKeyword` (0x10000)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|12|Thread für parallele Garbage Collection beendet wurde.|

Dieses Ereignis weist keine Ereignisdaten auf.

## <a name="gcfinalizersbegin_v1-event"></a>GCFinalizersBegin_V1 Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|14|Die Ausführung von Finalizern gestartet wird.|

Dieses Ereignis weist keine Ereignisdaten auf.

## <a name="gcfinalizersend_v1-event"></a>GCFinalizersEnd_V1 Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|13|Die Ausführung von Finalizern beendet wird.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|Die Anzahl der ausgeführten Finalizer.|
|`ClrInstanceID`|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="setgchandle-event"></a>Setgchandle-Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCHandleKeyword` 0x2|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`SetGCHandle`|30|Ein GC-Handle wurde festgelegt.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|Die Adresse des zugewiesenen Handles.|
|`ObjectID`|`win:Pointer`|Die Adresse des Objekts, dessen Handle erstellt wurde.|
|`Kind`|`win:UInt32`|Der Typ des festgelegten GC-Handles. <br /><br />`0x0`: Weakshort <br/><br/>`0x1`: Weaklong <br /><br />`0x2`: Strong <br /><br />`0x3`: Fixiert <br /><br />`0x4`: Variable<br /><br />`0x5`: Neu gezählt <br /><br />`0x6`: Abhängig<br /><br />`0x7`: Asyncpinned<br /><br />`0x8`: Sizedref|
|`Generation`|`win:UInt32`|Die Generierung des Objekts, dessen Handle erstellt wurde.|
|`AppDomainID`|`win:UInt64`|Die AppDomain-ID.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="destroygchandle-event"></a>Destroygchandle-Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCHandleKeyword` 0x2|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`DestroyGCHandle`|31|Ein GC-Handle wird zerstört.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|Die Adresse des zerstörten Handles.|
|`ClrInstanceID`|win:UInt16|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="pinobjectatgctime-event"></a>Pinobjectatgctime-Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Ausführlich (5)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`PinObjectAtGCTime`|33|Ein Objekt wurde während einer GC angeheftet.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|Die Adresse des Handles.|
|`ObjectID`|`win:Pointer`|Die Adresse des fixierten Objekts.|
|`ObjectSize`|`win:UInt64`|Die Größe des fixierten Objekts.|
|`TypeName`|`win:UnicodeString`|Der Name des Typs des fixierten Objekts.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="gctriggered-event"></a>Gcausgelöstes Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Ausführlich (5)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`GCTriggered`|33|Ein GC wurde ausgelöst.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`Reason`|`win:UInt32`|Der Grund für die Auslösung eines GC.<br/><br/>`0x0`: Zuordnung<br/><br/>`0x1`: Induziert <br/><br/>`0x2`: Lowmemory <br/><br/>`0x3`: Leer <br/><br/>`0x4`: Zuweisung <br/><br/>`0x5`: Outhf spacesmallobjecderap <br/><br/>`0x6`: Outhf spacelargeobjecthap <br/><br/>`0x7`: Inducednoforce <br/><br/>`0x8`: Belastung <br/><br/>`0x9`: Inducedlowmemory|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="increasememorypressure-event"></a>"Ewememorypressure"-Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informationen (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|----------------|---------------|-----------------|
|`IncreaseMemoryPressure`|200|Hohe Arbeitsspeicher Auslastung.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ClrInstanceID`|win:UInt16|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="decreasememorypressure-event"></a>Decreasememorypressure-Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informationen (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|----------------|---------------|-----------------|
|`DecreaseMemoryPressure`|201|Der Arbeitsspeicher Mangel wurde verringert.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`BytesFreed`|`win:UInt32`|Freigegebene Bytes.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="gcmarkwithtype-event"></a>Gcmarkwithtype-Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informationen (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|----------------|---------------|-----------------|
|`GCMarkWithType`|202|Ein GC-Stamm wurde während der GC-Markierungs Phase gekennzeichnet.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`HeapNum`|`win:UInt32`|Die heapnummer.|
|`ClrInstanceID`|win:UInt16|Eindeutige ID für die CoreCLR-Instanz.|
|`Type`|`win:UInt32`|Der GC-Stammtyp.<br/><br/>`0x0`: Stapel<br/><br/>`0x1`: Finalizer<br/><br/>`0x2`: Handle<br/><br/>`0x3`: Älter<br/><br/>`0x4`: Sizedref<br/><br/>`0x5`: Überlauf<br/><br/>|
|`Bytes`|`win:UInt64`|Die Anzahl der markierten bytes.|

## <a name="gcjoin_v2-event"></a>GCJoin_V2 Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Ausführlich (5)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`GCJoin_V2`|203|Ein mit einem GC verbundenen Thread.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`Heap`|`win:UInt32`|Heap Nummer|
|`JoinTime`|`win:UInt32`|Gibt an, ob dieses Ereignis am Anfang eines Joins oder Endes eines Joins ausgelöst wird ( `0x0` für Join-Start, `0x1` für joinende).|
|`JoinType`|`win:UInt32`|Der Jointyp. <br/><br/>`0x0`: Letzter Join<br/><br/>`0x1`: Join <br/><br/>`0x2`: Neu starten <br/><br/>`0x3`: Erster umgekehrter Join<br/><br/>`0x4`: Umgekehrter Join<br/><br/>|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|
