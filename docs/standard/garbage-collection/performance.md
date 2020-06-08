---
title: Garbage Collection und Leistung
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, troubleshooting
- garbage collection, performance
ms.assetid: c203467b-e95c-4ccf-b30b-953eb3463134
ms.openlocfilehash: 1d9c72a64d172dcadf1bff1b1edf3050ca5f7d05
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287622"
---
# <a name="garbage-collection-and-performance"></a>Garbage Collection und Leistung

In diesem Thema werden Probleme im Zusammenhang mit Garbage Collection und Speicherauslastung besprochen. Es werden Probleme beschrieben, die den verwalteten Heap betreffen, und es wird erläutert, wie die Auswirkungen der Garbage Collection auf Ihre Anwendungen minimiert werden können. Jedes Problem bietet Links zu Verfahren, mit denen Sie die Probleme untersuchen können.

## <a name="performance-analysis-tools"></a>Tools zur Leistungsanalyse

In den folgenden Abschnitten werden Tools beschrieben, die zum Untersuchen von Problemen mit der Speicherauslastung und Garbage Collection verfügbar sind. Die [Prozeduren](#performance-check-procedures), die weiter unten in diesem Thema aufgeführt sind, beziehen sich auf diese Tools.

### <a name="memory-performance-counters"></a>Speicherleistungsindikatoren

Sie können Leistungsindikatoren verwenden, um Leistungsdaten zu erfassen. Anweisungen hierzu finden Sie unter [Laufzeit-Profilerstellung](../../framework/debug-trace-profile/runtime-profiling.md). Die Leistungsindikatorkategorie .NET CLR-Speicher, die in [Leistungsindikatoren in .NET Framework](../../framework/debug-trace-profile/performance-counters.md) beschrieben wird, stellt Informationen über den Garbage Collector bereit.

### <a name="debugging-with-sos"></a>Debuggen mit SOS

Sie können den [Windows-Debugger (WinDbg)](/windows-hardware/drivers/debugger/index) verwenden, um Objekte auf dem verwalteten Heap zu überprüfen.

Wenn Sie WinDbg installieren möchten, installieren Sie die Debugtools für Windows über die Seite [Download Debugging Tools for Windows (Herunterladen von Debuggingtools für Windows)](/windows-hardware/drivers/debugger/debugger-download-tools).

### <a name="garbage-collection-etw-events"></a>Garbage Collection-ETW-Ereignisse

Die Ereignisablaufverfolgung für Windows (ETW) ist ein Ablaufverfolgungssystem, das die Profilerstellung und das Debugging ergänzt, die von .NET Framework bereitgestellt werden. Ab .NET Framework 4 erfassen [ETW-Ereignisse der Garbage Collection](../../framework/performance/garbage-collection-etw-events.md) nützliche Informationen für eine statistische Analyse des verwalteten Heaps. Beispielsweise liefert das `GCStart_V1`-Ereignis, das ausgelöst wird, sobald eine Garbage Collection durchgeführt wird, die folgenden Informationen:

- Welche Generation von Objekten wird erfasst.

- Was hat die Garbage Collection ausgelöst.

- Typ der Garbage Collection (gleichzeitig oder nicht gleichzeitig).

Die ETW-Ereignisprotokollierung ist effizient und wird keine Leistungsprobleme bei der Garbage Collection maskieren. Ein Prozess kann seine eigenen Ereignisse zusätzlich zu den ETW-Ereignissen bereitstellen. Bei der Protokollierung können die Ereignisse der Anwendung und die Garbage Collection-Ereignisse korreliert werden, um zu bestimmen, wie und wann Probleme mit dem Heap auftreten. Beispielsweise könnte eine Serveranwendung Ereignisse am Anfang und am Ende einer Clientanforderung bereitstellen.

### <a name="the-profiling-api"></a>Die Profilerstellungs-API

Die Profilerstellungsschnittstellen der Common Language Runtime (CLR) enthalten ausführliche Informationen zu den Objekten, die von einer Garbage Collection betroffen sind. Ein Profiler kann benachrichtigt werden, wenn eine Garbage Collection beginnt oder endet. Es kann Berichte über die Objekte im verwalteten Heap bereitstellen, einschließlich einer Identifikation von Objekten in jeder Generation. Weitere Informationen finden Sie unter [Übersicht über die Profilerstellung](../../framework/unmanaged-api/profiling/profiling-overview.md).

Profiler können umfassende Informationen bereitstellen. Allerdings können komplexe Profiler das Verhalten der Anwendung beeinflussen.

### <a name="application-domain-resource-monitoring"></a>Überwachung von Anwendungsdomänenressourcen

Ab .NET Framework 4 können Hosts mit der Ressourcenüberwachung für die Anwendungsdomäne (Application domain Resource Monitoring, ARM) die CPU- und Speicherauslastung pro Anwendungsdomäne überwachen. Weitere Informationen finden Sie unter [Überwachung von Anwendungsdomänenressourcen](app-domain-resource-monitoring.md).

## <a name="troubleshooting-performance-issues"></a>Problembehandlung bei Performanceproblemen

Der erste Schritt besteht darin, [zu bestimmen, ob das Problem tatsächlich bei der Garbage Collection liegt](#IsGC). Wenn dies der Fall ist, treffen Sie eine Auswahl in der folgenden Liste, um das Problem zu beheben.

- [Es wird eine Ausnahme aufgrund ungenügenden Arbeitsspeichers ausgelöst](#Issue_OOM)

- [Der Prozess verwendet zu viel Arbeitsspeicher](#Issue_TooMuchMemory)

- [Der Garbage Collector gibt Objekte nicht schnell genug frei](#Issue_NotFastEnough)

- [Der verwaltete Heap ist zu sehr fragmentiert](#Issue_Fragmentation)

- [Die Pausen der Garbage Collections sind zu lang](#Issue_LongPauses)

- [Generation 0 ist zu groß](#Issue_Gen0)

- [Die CPU-Auslastung während einer Garbage Collection ist zu hoch](#Issue_HighCPU)

<a name="Issue_OOM"></a>

### <a name="issue-an-out-of-memory-exception-is-thrown"></a>Problem: Es wird eine Ausnahme aufgrund ungenügenden Arbeitsspeichers ausgelöst

Es gibt zwei legitime Fälle, in denen eine verwaltete <xref:System.OutOfMemoryException> ausgelöst werden kann:

- Ungenügender virtueller Arbeitsspeicher.

  Der Garbage Collector belegt Systemspeicher in Segmenten mit einer vordefinierten Größe. Wenn eine Belegung ein zusätzliches Segment erfordert, jedoch kein freier zusammenhängender Block im virtuellen Arbeitsspeicher des Prozesses vorhanden ist, schlägt die Zuordnung für den verwalteten Heap fehl.

- Ungenügender physischer Arbeitsspeicher für eine Belegung.

|Überprüfen der Leistung|
|------------------------|
|[Bestimmen Sie, ob die Ausnahme aufgrund ungenügenden Arbeitsspeichers verwaltet ist.](#OOMIsManaged)<br /><br /> [Ermitteln Sie, wie viel virtueller Speicher reserviert werden kann.](#GetVM)<br /><br /> [Bestimmen Sie, ob ausreichend physikalischer Speicher vorhanden ist.](#Physical)|

Wenn Sie feststellen, dass die Ausnahme nicht legitim ist, wenden Sie sich mit folgenden Informationen an den Kundenservice und Support von Microsoft:

- Der Stapel mit der verwalteten Ausnahme aufgrund ungenügenden Arbeitsspeichers.

- Vollständiges Speicherabbild.

- Daten, die zeigen, dass es sich nicht um eine legitime Ausnahme aufgrund ungenügenden Arbeitsspeichers handelt, einschließlich Daten, die zeigen, dass virtueller oder physischer Speicher kein Problem darstellt.

<a name="Issue_TooMuchMemory"></a>

### <a name="issue-the-process-uses-too-much-memory"></a>Problem: Der Prozess verwendet zu viel Arbeitsspeicher

Eine häufige Annahme ist, dass die Speicherauslastungsanzeige auf der Registerkarte **Leistung** des Windows Task-Managers anzeigen kann, wann zu viel Arbeitsspeicher verwendet wird. Allerdings betrifft diese Anzeige lediglich das Workingset. Sie stellt keine Informationen zur virtuellen Arbeitsspeicherverwendung bereit.

Wenn Sie feststellen, dass das Problem durch den verwalteten Heap verursacht wird, müssen Sie den verwalteten Heap über einen bestimmten Zeitraum überwachen, um ein Muster zu ermitteln.

Wenn Sie feststellen, dass das Problem nicht durch den verwalteten Heap verursacht wird, müssen Sie ein systemeigenes Debugging durchführen.

|Überprüfen der Leistung|
|------------------------|
|[Ermitteln Sie, wie viel virtueller Speicher reserviert werden kann.](#GetVM)<br /><br /> [Bestimmen Sie, wie viel Arbeitsspeicher der verwaltete Heap zusichert.](#ManagedHeapCommit)<br /><br /> [Bestimmen Sie, wie viel Arbeitsspeicher der verwaltete Heap reserviert.](#ManagedHeapReserve)<br /><br /> [Bestimmen Sie große Objekte in Generation 2.](#ExamineGen2)<br /><br /> [Bestimmen Sie die Verweise auf Objekte.](#ObjRef)|

<a name="Issue_NotFastEnough"></a>

### <a name="issue-the-garbage-collector-does-not-reclaim-objects-fast-enough"></a>Problem: Der Garbage Collector gibt Objekte nicht schnell genug frei

Wenn es scheint, als ob Objekte nicht wie erwartet von der Garbage Collection freigegeben werden, müssen Sie ermitteln, ob starke Verweise auf diese Objekte vorhanden sind.

Dieses Problem kann auch auftreten, wenn keine Garbage Collection für die Generation durchgeführt wurde, die ein totes Objekt enthält. Dies zeigt an, dass der Finalizer für die inaktiven Objekt nicht ausgeführt wurde. Dies ist z. B. möglich, wenn Sie eine Anwendung mit einem Singlethread-Apartment (STA) ausführen und der Thread, der die Warteschlange des Finalizers verwaltet, keinen Aufruf in das Apartment ausführen kann.

|Überprüfen der Leistung|
|------------------------|
|[Überprüfen Sie die Verweise auf Objekte.](#ObjRef)<br /><br /> [Bestimmen Sie, ob ein Finalizer ausgeführt wurde.](#Induce)<br /><br /> [Bestimmen Sie, ob Objekte auf einen Abschluss warten.](#Finalize)|

<a name="Issue_Fragmentation"></a>

### <a name="issue-the-managed-heap-is-too-fragmented"></a>Problem: Der verwaltete Heap ist zu sehr fragmentiert

Der Fragmentierungsgrad wird als das Verhältnis zwischen freiem Speicherplatz und dem insgesamt belegten Speicher für die Generation berechnet. Für Generation 2 gelten nicht mehr als 20% als akzeptabler Wert für die Fragmentierung. Da Generation 2 sehr groß werden kann, ist das Verhältnis der Fragmentierung wichtiger als der absolute Wert.

Viele freier Speicherplatz in Generation 0 ist kein Problem, da in dieser Generation neue Objekte belegt werden.

Fragmentierung tritt immer im Heap für große Objekte auf, da dieser nicht komprimiert ist. Freie einander angrenzende Objekte werden immer in einem einzelnen Bereich zusammengefasst, um große Objektanforderungen erfüllen zu können.

Die Fragmentierung kann in Generation 1 und in Generation 2 zu einem Problem werden. Wenn diese Generationen nach einer Garbage Collection viel freien Speicherplatz aufweisen, muss die Objektverwendung einer Anwendung möglicherweise angepasst werden, und Sie sollten die Lebensdauer von langfristigen Objekten neu prüfen.

Ein übermäßiges Fixieren von Objekten kann die Fragmentierung erhöhen. Wenn die Fragmentierung zu groß ist, wurden möglicherweise zu viele Objekte fixiert.

Wenn die Fragmentierung des virtuellen Arbeitsspeichers verhindert, dass der Garbage Collector Segmente hinzufügen kann, kann dies eine der folgenden Ursachen haben:

- Häufiges Laden und Entladen von vielen kleinen Assemblys.

- Zu viele Verweise auf COM-Objekte bei der Interoperation mit nicht verwaltetem Code.

- Erstellung von großen flüchtigen Objekten. Dies zwingt den großen Objektheap, häufig Heapsgmente zu reservieren und wieder freizugeben.

  Wenn die CLR gehostet wird, kann eine Anwendung anfordern, dass der Garbage Collector seine Segmente beibehält. Dadurch wird die Häufigkeit von Segmentbelegungen reduziert. Dies wird mit dem Flag STARTUP_HOARD_GC_VM in der [STARTUP_FLAGS-Enumeration](../../framework/unmanaged-api/hosting/startup-flags-enumeration.md) erreicht.

|Überprüfen der Leistung|
|------------------------|
|[Bestimmen Sie den freien Speicherplatz im verwalteten Heap.](#Fragmented)<br /><br /> [Bestimmen Sie die Anzahl der fixierten Objekte.](#Pinned)|

Wenn Sie glauben, dass keine legitime Ursache für die Fragmentierung vorliegt, wenden Sie sich an den Kundenservice und Support von Microsoft.

<a name="Issue_LongPauses"></a>

### <a name="issue-garbage-collection-pauses-are-too-long"></a>Problem: Die Pausen der Garbage Collections sind zu lang

Die Garbage Collection arbeitet in verzögerter Echtzeit. Daher muss eine Anwendung gewisse Pausen tolerieren können. Ein Kriterium für die verzögerte Echtzeit besteht darin, dass 95% der Vorgänge zeitgenau beendet werden müssen.

Bei der gleichzeitigen Garbage Collection dürfen während einer Garbage Collection verwaltete Threads ausgeführt werden. Dies bedeutet, dass die Pausen sehr klein sind.

Kurzlebige Garbage Collections (Generationen 0 und 1) dauern nur einige Millisekunden, sodass das Verringern der Pausen normalerweise nicht sinnvoll ist. Sie können jedoch die Pausen in Garbage Collections der Generation 2 verringern, indem Sie das Muster der Belegungsanforderungen in einer Anwendung anpassen.

Eine andere und genauere Methode ist die Verwendung von [ETW-Ereignissen der Garbage Collection](../../framework/performance/garbage-collection-etw-events.md). Sie können die Intervalle der Collections ermitteln, indem Sie die Zeitstempeldifferenzen einer bestimmten Ereignissequenz addieren. Die gesamte Collection-Sequenz beinhaltet die Unterbrechung der Ausführungs-Engine, die Garbage Collection selbst und die Wiederaufnahme der Ausführungs-Engine.

Verwenden Sie [Garbage Collection-Benachrichtigungen](notifications.md), um zu ermitteln, ob ein Server im Begriff ist, eine Collection der Generation 2 durchzuführen, und ob Umleitungsanforderungen an einen anderen Server die Probleme mit Pausen verringern könnten.

|Überprüfen der Leistung|
|------------------------|
|[Bestimmen Sie die Dauer einer Garbage Collection.](#TimeInGC)<br /><br /> [Ermitteln Sie, was eine Garbage Collection ausgelöst hat.](#Triggered)|

<a name="Issue_Gen0"></a>

### <a name="issue-generation-0-is-too-big"></a>Problem: Generation 0 ist zu groß

Generation 0 enthält auf einem 64-Bit-System häufig eine größere Anzahl von Objekten, insbesondere, wenn Sie die Garbage Collection auf dem Server statt der Garbage Collection für die Arbeitsstation verwenden. Dies liegt daran, dass der Schwellenwert zum Auslösen einer Garbage Collection der Generation 0 in dieser Umgebung höher ist und Collections der Generation 0 viel größer werden können. Die Leistung wird verbessert, wenn eine Anwendung mehr Arbeitsspeicher belegt, bevor eine Garbage Collection ausgelöst wird.

<a name="Issue_HighCPU"></a>

### <a name="issue-cpu-usage-during-a-garbage-collection-is-too-high"></a>Problem: Die CPU-Auslastung während einer Garbage Collection ist zu hoch

Die CPU-Auslastung ist während einer Garbage Collection hoch. Wenn sehr viel Prozessorzeit für eine Garbage Collection aufgewendet wird, erfolgen die Collections zu häufig, oder die Collection dauert zu lang. Eine zu hohe Belegungsrate für Objekte auf dem verwalteten Heap führt zu häufigeren Garbage Collections. Das Verringern der Belegungsrate verringert die Häufigkeit der Garbage Collections.

Sie können die Belegungsrate mit dem Leistungsindikator `Allocated Bytes/second` überwachen. Weitere Informationen finden Sie unter [Leistungsindikatoren in .NET Framework](../../framework/debug-trace-profile/performance-counters.md).

Die Dauer einer Collection wird wesentlich durch die Anzahl der Objekte bestimmt, die nach der Belegung noch vorhanden sind. Der Garbage Collector muss einen sehr großen Speicherbereich durchlaufen, wenn viele freizugebende Objekte verblieben sind. Der Aufwand für die Komprimierung der Überlebenden ist sehr zeitintensiv. Um zu bestimmen, wie viele Objekte während einer Collection verarbeitet wurden, legen Sie einen Haltepunkt im Debugger am Ende einer Garbage Collection für eine bestimmte Generation fest.

|Überprüfen der Leistung|
|------------------------|
|[Ermitteln Sie, ob die hohe CPU-Auslastung durch die Garbage Collection verursacht wird.](#HighCPU)<br /><br /> [Legen Sie einen Haltepunkt am Ende der Garbage Collection fest.](#GenBreak)|

## <a name="troubleshooting-guidelines"></a>Richtlinien für die Problembehandlung

In diesem Abschnitt werden Richtlinien beschrieben, die Sie zu Beginn der Prüfungen und Analysen berücksichtigen sollten.

### <a name="workstation-or-server-garbage-collection"></a>Garbage Collection für die Arbeitsstation oder Garbage Collection auf dem Server

Ermitteln Sie, ob Sie den richtigen Typ der Garbage Collection verwenden. Wenn Ihre Anwendung mehrere Threads und Objektinstanzen verwendet, verwenden Sie die Garbage Collection auf dem Server statt der Garbage Collection für die Arbeitsstation. Die Garbage Collection auf dem Server kann in mehreren Threads ausgeführt werden, wohingegen die Garbage Collection für die Arbeitsstation erfordert, dass mehrere Instanzen einer Anwendung eigene Garbage Collection-Threads ausführen, die um die Prozessorzeit konkurrieren.

Eine Anwendung mit einer geringen Auslastung, die nur selten im Hintergrund Aufgaben ausführt, z. B. ein Dienst, kann die Garbage Collection für die Arbeitsstation mit deaktivierter gleichzeitiger Garbage Collection verwenden.

### <a name="when-to-measure-the-managed-heap-size"></a>Wann sollte die Größe des verwalteten Heaps gemessen werden

Sofern Sie keinen Profiler verwenden, müssen Sie ein einheitliches Messmuster erzielen, um Leistungsprobleme effektiv bestimmen zu können. Beachten Sie bei der Messplanung die folgenden Punkte:

- Wenn Sie nach einer Garbage Collection in Generation 2 messen, ist der gesamte verwaltete Heap frei von inaktiven Objekten.

- Wenn Sie sofort nach einer Garbage Collection in Generation 0 messen, wurden die Objekte in den Generationen 1 und 2 noch nicht freigegeben.

- Wenn Sie direkt vor einer Garbage Collection messen, messen Sie die maximale Belegung vor Beginn der Garbage Collection.

- Das Messen während einer Garbage Collection ist problematisch, da die Garbage Collector-Datenstrukturen sich nicht in einem gültigen Zustand für einen Durchlauf befinden und möglicherweise nicht in der Lage sind, vollständige Ergebnisse zu liefern. Dieser Fehler ist entwurfsbedingt.

- Wenn Sie die Garbage Collection für die Arbeitsstation mit gleichzeitiger Garbage Collection verwenden, werden die freigegebenen Objekte nicht komprimiert, sodass die Heapgröße identisch oder größer sein kann (sie kann durch die Fragmentierung größer erscheinen).

- Die gleichzeitige Garbage Collection in Generation 2 wird verzögert, wenn die Auslastung des physischen Arbeitsspeichers zu hoch ist.

Im folgenden Verfahren wird beschrieben, wie Sie einen Haltepunkt festlegen, sodass Sie den verwalteten Heap messen können.

<a name="GenBreak"></a>

#### <a name="to-set-a-breakpoint-at-the-end-of-garbage-collection"></a>So legen Sie einen Haltepunkt am Ende der Garbage Collection fest

- Geben Sie in WinDbg bei geladener SOS-Debuggererweiterung folgenden Befehl ein:

  **bp mscorwks!WKS::GCHeap::RestartEE "j (dwo(mscorwks!WKS::GCHeap::GcCondemnedGeneration)==2) 'kb';'g'"**

  wobei **GcCondemnedGeneration** auf die gewünschte Generation festgelegt ist. Dieser Befehl erfordert private Symbole.

  Mit diesem Befehl wird eine Unterbrechung erzwungen, wenn **RestartEE** ausgeführt wird, nachdem die Objekte der Generation 2 für die Garbage Collection freigegeben wurden.

  Bei der Garbage Collection auf dem Server ruft nur ein Thread **RestartEE** auf, sodass der Haltepunkt nur einmal während einer Garbage Collection der Generation 2 angelaufen wird.

## <a name="performance-check-procedures"></a>Prozeduren zur Leistungsüberprüfung

In diesem Abschnitt werden die folgenden Verfahren beschrieben, um die Ursache des Leistungsproblems zu isolieren:

- [Stellen Sie fest, ob das Problem durch die Garbage Collection verursacht wird.](#IsGC)

- [Bestimmen Sie, ob die Ausnahme aufgrund ungenügenden Arbeitsspeichers verwaltet ist.](#OOMIsManaged)

- [Ermitteln Sie, wie viel virtueller Speicher reserviert werden kann.](#GetVM)

- [Bestimmen Sie, ob ausreichend physikalischer Speicher vorhanden ist.](#Physical)

- [Bestimmen Sie, wie viel Arbeitsspeicher der verwaltete Heap zusichert.](#ManagedHeapCommit)

- [Bestimmen Sie, wie viel Arbeitsspeicher der verwaltete Heap reserviert.](#ManagedHeapReserve)

- [Bestimmen Sie große Objekte in Generation 2.](#ExamineGen2)

- [Bestimmen Sie die Verweise auf Objekte.](#ObjRef)

- [Bestimmen Sie, ob ein Finalizer ausgeführt wurde.](#Induce)

- [Bestimmen Sie, ob Objekte auf einen Abschluss warten.](#Finalize)

- [Bestimmen Sie den freien Speicherplatz im verwalteten Heap.](#Fragmented)

- [Bestimmen Sie die Anzahl der fixierten Objekte.](#Pinned)

- [Bestimmen Sie die Dauer einer Garbage Collection.](#TimeInGC)

- [Ermitteln Sie, was eine Garbage Collection ausgelöst hat.](#Triggered)

- [Ermitteln Sie, ob die hohe CPU-Auslastung durch die Garbage Collection verursacht wird.](#HighCPU)

<a name="IsGC"></a>

### <a name="to-determine-whether-the-problem-is-caused-by-garbage-collection"></a>So stellen Sie fest, ob das Problem durch die Garbage Collection verursacht wird

- Überprüfen Sie die folgenden beiden Leistungsindikatoren für den Arbeitsspeicher:

  - **GC-Zeitdauer in Prozent**. Zeigt an, wie viel Prozent der vergangenen Zeit seit dem letzten Garbage Collection-Durchlauf mit der Durchführung der Garbage Collection verbracht wurde. Mit diesem Indikator können Sie bestimmen, ob die Garbage Collection zu viel Zeit benötigt, um Speicherplatz auf dem verwalteten Heap verfügbar zu machen. Wenn die für die Garbage Collection aufgewendete Zeit relativ gering ist, kann dies auf ein Ressourcenproblem außerhalb des verwalteten Heaps hindeuten. Dieser Indikator ist möglicherweise nicht präzise, wenn die gleichzeitige oder die Garbage Collection im Hintergrund aktiviert ist.

  - **Zugesicherte Bytes gesamt**. Zeigt den virtuellen Speicher an, der momentan durch den Garbage Collector belegt ist. Mit diesem Indikator können Sie bestimmen, ob der Garbage Collector einen übermäßig großen Teil des Arbeitsspeichers im Verhältnis zur Anwendung selbst belegt.

  Die meisten Speicherleistungsindikatoren werden am Ende jeder Garbage Collection aktualisiert. Daher geben sie möglicherweise nicht die aktuellen Bedingungen an, zu denen Sie Informationen benötigen.

<a name="OOMIsManaged"></a>

### <a name="to-determine-whether-the-out-of-memory-exception-is-managed"></a>So bestimmen Sie, ob die Ausnahme aufgrund ungenügenden Arbeitsspeichers verwaltet ist

1. Geben Sie im WinDbg-Debugger oder im Visual Studio-Debugger bei geladener SOS-Debuggererweiterung den Befehl zur Ausgabe von Ausnahmen (**pe**) ein:

    **!pe**

    Wenn die Ausnahme verwaltet ist, wird <xref:System.OutOfMemoryException> als Ausnahmetyp angezeigt, wie im folgenden Beispiel dargestellt.

    ```console
    Exception object: 39594518
    Exception type: System.OutOfMemoryException
    Message: <none>
    InnerException: <none>
    StackTrace (generated):
    ```

2. Wenn die Ausgabe keine Ausnahme angibt, müssen Sie ermitteln, welcher Thread die Ausnahme aufgrund ungenügenden Arbeitsspeichers ausgelöst hat. Geben Sie im Debugger den folgenden Befehl ein, um alle Threads mit ihren Aufruflisten anzuzeigen:

    **~\*kb**

    Der Thread mit dem Stapel, der Ausnahmeaufrufe enthält, wird durch das `RaiseTheException`-Argument angegeben. Dies ist das verwaltete Ausnahmeobjekt.

    ```console
    28adfb44 7923918f 5b61f2b4 00000000 5b61f2b4 mscorwks!RaiseTheException+0xa0
    ```

3. Sie können den folgenden Befehl verwenden, um geschachtelte Ausnahmen zu speichern.

    **!pe -nested**

    Wenn Sie keine Ausnahmen finden können, stammt die Ausnahme aufgrund ungenügenden Arbeitsspeichers aus nicht verwaltetem Code.

<a name="GetVM"></a>

### <a name="to-determine-how-much-virtual-memory-can-be-reserved"></a>So ermitteln Sie, wie viel virtueller Speicher reserviert werden kann

- Geben Sie in WinDbg bei geladener SOS-Debuggererweiterung folgenden Befehl ein, um den größten freien Bereich abzurufen:

  **!address -summary**

  Der größte freie Bereich wird wie in der folgenden Ausgabe angezeigt.

  ```console
  Largest free region: Base 54000000 - Size 0003A980
  ```

  In diesem Beispiel ist die Größe des größten freien Bereichs ungefähr 24.000 KB (3A980 als Hexadezimalwert). Dieser Bereich ist wesentlich kleiner als der Bereich, den die Garbage Collection für ein Segment benötigt.

  - oder -

- Verwenden Sie den Befehl **vmstat**:

  **!vmstat**

  Der größte freie Bereich ist der größte Wert in der Spalte MAXIMUM, wie in der folgenden Ausgabe gezeigt.

  ```console
  TYPE        MINIMUM   MAXIMUM     AVERAGE   BLK COUNT   TOTAL
  ~~~~        ~~~~~~~   ~~~~~~~     ~~~~~~~   ~~~~~~~~~~  ~~~~
  Free:
  Small       8K        64K         46K       36          1,671K
  Medium      80K       864K        349K      3           1,047K
  Large       1,384K    1,278,848K  151,834K  12          1,822,015K
  Summary     8K        1,278,848K  35,779K   51          1,824,735K
  ```

<a name="Physical"></a>

### <a name="to-determine-whether-there-is-enough-physical-memory"></a>So bestimmen Sie, ob ausreichend physikalischer Speicher vorhanden ist

1. Starten Sie Windows Task-Manager.

2. Prüfen Sie auf der Registerkarte **Leistung** den zugesicherten Wert. (Prüfen Sie unter Windows 7 den Wert **Zugesichert (KB)** in der **Systemgruppe**.)

    Wenn **Gesamt** nahe der **Grenze** ist, ist nicht genügend physischer Arbeitsspeicher verfügbar.

<a name="ManagedHeapCommit"></a>

### <a name="to-determine-how-much-memory-the-managed-heap-is-committing"></a>So bestimmen Sie, wie viel Arbeitsspeicher der verwaltete Heap zusichert

- Verwenden Sie den Speicherleistungsindikator `# Total committed bytes`, um die Anzahl an Bytes abzurufen, die der verwaltete Heap zusichert. Der Garbage Collector sichert nach Bedarf Ausschnitte in einem Segment zu, niemals alle zur selben Zeit.

  > [!NOTE]
  > Verwenden Sie nicht den Leistungsindikator `# Bytes in all Heaps`, da dieser nicht die tatsächliche Speicherauslastung des verwalteten Heaps angibt. Die Größe einer Generation ist in diesem Wert enthalten, und es handelt sich eigentlich um den Schwellenwert, d. h. um die Größe, bei der eine Garbage Collection ausgelöst wird, wenn die Generation mit Objekten gefüllt ist. Daher ist dieser Wert 0 (null).

<a name="ManagedHeapReserve"></a>

### <a name="to-determine-how-much-memory-the-managed-heap-reserves"></a>So bestimmen Sie, wie viel Arbeitsspeicher der verwaltete Heap reserviert

- Verwenden Sie den Speicherleistungsindikator `# Total reserved bytes`.

  Der Garbage Collector reserviert Speicherplatz in Segmenten. Sie können den Anfang eines Segments ermitteln, indem Sie den Befehl **eeheap** verwenden.

  > [!IMPORTANT]
  > Obwohl Sie die Größe des Arbeitsspeichers ermitteln können, der vom Garbage Collector für jedes Segment zugewiesen wird, ist die Segmentgröße von der Implementierung abhängig und kann jederzeit geändert werden, auch bei regelmäßigen Updates. Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen, und es darf in ihr auch nicht versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren.

- Geben Sie im WinDbg-Debugger oder im Visual Studio-Debugger bei geladener SOS-Debuggererweiterung den folgenden Befehl ein:

  **!eeheap -gc**

  Daraus ergibt sich folgendes Ergebnis.

  ```console
  Number of GC Heaps: 2
  ------------------------------
  Heap 0 (002db550)
  generation 0 starts at 0x02abe29c
  generation 1 starts at 0x02abdd08
  generation 2 starts at 0x02ab0038
  ephemeral segment allocation context: none
    segment    begin allocated     size
  02ab0000 02ab0038  02aceff4 0x0001efbc(126908)
  Large object heap starts at 0x0aab0038
    segment    begin allocated     size
  0aab0000 0aab0038  0aab2278 0x00002240(8768)
  Heap Size   0x211fc(135676)
  ------------------------------
  Heap 1 (002dc958)
  generation 0 starts at 0x06ab1bd8
  generation 1 starts at 0x06ab1bcc
  generation 2 starts at 0x06ab0038
  ephemeral segment allocation context: none
    segment    begin allocated     size
  06ab0000 06ab0038  06ab3be4 0x00003bac(15276)
  Large object heap starts at 0x0cab0038
    segment    begin allocated     size
  0cab0000 0cab0038  0cab0048 0x00000010(16)
  Heap Size    0x3bbc(15292)
  ------------------------------
  GC Heap Size   0x24db8(150968)
  ```

  Die Adressen, die durch "segment" angegeben werden, sind die Startadressen der Segmente.

<a name="ExamineGen2"></a>

### <a name="to-determine-large-objects-in-generation-2"></a>So bestimmen Sie große Objekte in Generation 2

- Geben Sie im WinDbg-Debugger oder im Visual Studio-Debugger bei geladener SOS-Debuggererweiterung den folgenden Befehl ein:

  **!dumpheap –stat**

  Wenn der verwaltete Heap groß ist, kann die Ausführung von **dumpheap** eine Weile dauern.

  Sie können die Analyse in den letzten Zeilen der Ausgabe beginnen, da diese die Objekte auflisten, die den meisten Platz verwenden. Zum Beispiel:

  ```console
  2c6108d4   173712     14591808 DevExpress.XtraGrid.Views.Grid.ViewInfo.GridCellInfo
  00155f80      533     15216804      Free
  7a747c78   791070     15821400 System.Collections.Specialized.ListDictionary+DictionaryNode
  7a747bac   700930     19626040 System.Collections.Specialized.ListDictionary
  2c64e36c    78644     20762016 DevExpress.XtraEditors.ViewInfo.TextEditViewInfo
  79124228   121143     29064120 System.Object[]
  035f0ee4    81626     35588936 Toolkit.TlkOrder
  00fcae40     6193     44911636 WaveBasedStrategy.Tick_Snap[]
  791242ec    40182     90664128 System.Collections.Hashtable+bucket[]
  790fa3e0  3154024    137881448 System.String
  Total 8454945 objects
  ```

  Das letzte aufgelistete Objekt ist eine Zeichenfolge, die den meisten Platz beansprucht. Sie können Ihre Anwendung überprüfen, um zu ermitteln, wie die Zeichenfolgenobjekte optimiert werden können. Um Zeichenfolgen anzuzeigen, die zwischen 150 und 200 Byte groß sind, geben Sie Folgendes ein:

  **!dumpheap -type System.String -min 150 -max 200**

  Ein Beispielergebnis sieht wie folgt aus.

  ```console
  Address  MT           Size  Gen
  1875d2c0 790fa3e0      152    2 System.String HighlightNullStyle_Blotter_PendingOrder-11_Blotter_PendingOrder-11
  …
  ```

  Das Verwenden einer ganzen Zahl anstelle einer Zeichenfolge für eine ID kann effizienter sein. Wenn dieselbe Zeichenfolge viele tausend Mal wiederholt wird, sollten Sie eine Internalisierung der Zeichenfolgen in Betracht ziehen. Weitere Informationen zur Internalisierung von Zeichenfolgen finden Sie im Referenzthema für die <xref:System.String.Intern%2A?displayProperty=nameWithType>-Methode.

<a name="ObjRef"></a>

### <a name="to-determine-references-to-objects"></a>So bestimmen Sie Verweise auf Objekte

- Geben Sie in WinDbg bei geladener SOS-Debuggererweiterung folgenden Befehl ein, um Objektverweise aufzulisten:

  **!gcroot**

  `-or-`

- Um die Verweise für ein bestimmtes Objekt zu ermitteln, geben Sie zusätzlich die Adresse an:

  **!gcroot 1c37b2ac**

  Die Stammelemente, die in Stapeln gefunden werden, sind möglicherweise falsche positive Ergebnisse. Weitere Informationen erhalten Sie mit dem Befehl `!help gcroot`.

  ```console
  ebx:Root:19011c5c(System.Windows.Forms.Application+ThreadContext)->
  19010b78(DemoApp.FormDemoApp)->
  19011158(System.Windows.Forms.PropertyStore)->
  … [omitted]
  1c3745ec(System.Data.DataTable)->
  1c3747a8(System.Data.DataColumnCollection)->
  1c3747f8(System.Collections.Hashtable)->
  1c376590(System.Collections.Hashtable+bucket[])->
  1c376c98(System.Data.DataColumn)->
  1c37b270(System.Data.Common.DoubleStorage)->
  1c37b2ac(System.Double[])
  Scan Thread 0 OSTHread 99c
  Scan Thread 6 OSTHread 484
  ```

  Ein Ausführen des Befehls **gcroot** kann lange dauern. Jedes Objekt, das nicht von der Garbage Collection freigegeben wurde, ist ein aktives Objekt. Das heißt, dass ein Stamm direkt oder indirekt das Objekt hält, sodass **gcroot** Pfadinformationen zum Objekt zurückgeben sollte. Sie sollten die zurückgegebenen Diagramme untersuchen und feststellen, warum auf diese Objekte immer noch verwiesen wird.

<a name="Induce"></a>

### <a name="to-determine-whether-a-finalizer-has-been-run"></a>So bestimmen Sie, ob ein Finalizer ausgeführt wurde

- Führen Sie ein Testprogramm aus, das den folgenden Code enthält:

  ```csharp
  GC.Collect();
  GC.WaitForPendingFinalizers();
  GC.Collect();
  ```

  Wenn der Test das Problem behebt, heißt dies, dass der Garbage Collector keine Objekte freigegeben hat, da die Finalizer für diese Objekte unterbrochen wurden. Mithilfe der <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType>-Methode können die Finalizer ihre Aufgaben abschließen und das Problem beheben.

<a name="Finalize"></a>

### <a name="to-determine-whether-there-are-objects-waiting-to-be-finalized"></a>So bestimmen Sie, ob Objekte auf einen Abschluss warten

1. Geben Sie im WinDbg-Debugger oder im Visual Studio-Debugger bei geladener SOS-Debuggererweiterung den folgenden Befehl ein:

    **!finalizequeue**

    Prüfen Sie die Anzahl der Objekte, die auf einen Abschluss warten. Wenn die Zahl hoch ist, müssen Sie überprüfen, weshalb diese Finalizer nicht schnell genug bzw. überhaupt nicht fortgesetzt werden können.

2. Um eine Ausgabe der Threads abzurufen, geben Sie den folgenden Befehl ein:

    **threads -special**

    Dieser Befehl stellt folgende Ausgabe bereit.

    ```console
       OSID     Special thread type
    2    cd0    DbgHelper
    3    c18    Finalizer
    4    df0    GC SuspendEE
    ```

    Der Finalizerthread gibt an, welcher Finalizer, sofern vorhanden, aktuell ausgeführt wird. Wenn ein Finalizerthread keine Finalizer ausführt, wartet er auf ein Ereignis, das die Ausführung startet. Der Finalizerthread befindet sich meistens in diesem Zustand, da er mit THREAD_HIGHEST_PRIORITY ausgeführt wird und die Ausführung von Finalizern i. d. R. sehr schnell abschließen sollte.

<a name="Fragmented"></a>

### <a name="to-determine-the-amount-of-free-space-in-the-managed-heap"></a>So bestimmen Sie den freien Speicherplatz im verwalteten Heap

- Geben Sie im WinDbg-Debugger oder im Visual Studio-Debugger bei geladener SOS-Debuggererweiterung den folgenden Befehl ein:

  **!dumpheap -type Free -stat**

  Dieser Befehl zeigt die Gesamtgröße aller freien Objekte im verwalteten Heap an, wie im folgenden Beispiel gezeigt.

  ```console
  total 230 objects
  Statistics:
        MT    Count    TotalSize Class Name
  00152b18      230     40958584      Free
  Total 230 objects
  ```

- Um den freien Speicherplatz in Generation 0 zu ermitteln, geben Sie den folgenden Befehl ein, um Informationen zum Speicherverbrauch jeder Generation zu erhalten:

  **!eeheap -gc**

  Dieser Befehl zeigt eine Ausgabe ähnlich der folgenden an. Die letzte Zeile zeigt das kurzlebige Segment an.

  ```console
  Heap 0 (0015ad08)
  generation 0 starts at 0x49521f8c
  generation 1 starts at 0x494d7f64
  generation 2 starts at 0x007f0038
  ephemeral segment allocation context: none
  segment  begin     allocated  size
  00178250 7a80d84c  7a82f1cc   0x00021980(137600)
  00161918 78c50e40  78c7056c   0x0001f72c(128812)
  007f0000 007f0038  047eed28   0x03ffecf0(67103984)
  3a120000 3a120038  3a3e84f8   0x002c84c0(2917568)
  46120000 46120038  49e05d04   0x03ce5ccc(63855820)
  ```

- Berechnen Sie den Speicherplatz für Generation 0:

  **? 49e05d04-0x49521f8c**

  Daraus ergibt sich folgendes Ergebnis. Generation 0 belegt ungefähr 9 MB.

  ```console
  Evaluate expression: 9321848 = 008e3d78
  ```

- Der folgende Befehl gibt den freien Platz im Bereich der Generation 0 aus:

  **!dumpheap -type Free -stat 0x49521f8c 49e05d04**

  Daraus ergibt sich folgendes Ergebnis.

  ```console
  ------------------------------
  Heap 0
  total 409 objects
  ------------------------------
  Heap 1
  total 0 objects
  ------------------------------
  Heap 2
  total 0 objects
  ------------------------------
  Heap 3
  total 0 objects
  ------------------------------
  total 409 objects
  Statistics:
        MT    Count TotalSize Class Name
  0015a498      409   7296540      Free
  Total 409 objects
  ```

  Diese Ausgabe zeigt, dass der Bereich der Generation 0 im Heap 9 MB Speicherplatz für Objekte verwendet, von denen 7 MB frei sind. Diese Analyse zeigt, in welchem Maße Generation 0 zur Fragmentierung beiträgt. Dieser Anteil des verwendeten Heaps sollte, als Ursache für die Fragmentierung von Langzeitobjekten, von der Gesamtgröße abgezogen werden.

<a name="Pinned"></a>

### <a name="to-determine-the-number-of-pinned-objects"></a>So bestimmen Sie die Anzahl der fixierten Objekte

- Geben Sie im WinDbg-Debugger oder im Visual Studio-Debugger bei geladener SOS-Debuggererweiterung den folgenden Befehl ein:

  **!gchandles**

  Die angezeigte Statistik beinhaltet die Anzahl der festen Handles, wie im folgenden Beispiel gezeigt.

  ```console
  GC Handle Statistics:
  Strong Handles:      29
  Pinned Handles:      10
  ```

<a name="TimeInGC"></a>

### <a name="to-determine-the-length-of-time-in-a-garbage-collection"></a>So bestimmen Sie die Dauer einer Garbage Collection

- Überprüfen Sie den Speicherleistungsindikator `% Time in GC`.

  Der Wert wird anhand eines Samplingintervalls berechnet. Da die Indikatoren am Ende jeder Garbage Collection aktualisiert werden, hat die aktuelle Messung den gleichen Wert wie die vorhergehende Messung, wenn während des Intervalls keine Collections aufgetreten sind.

  Die Dauer der Collection wird durch die Multiplikation der Samplingintervalldauer mit dem Prozentwert ermittelt.

  Die folgenden Daten zeigen vier Messintervalle von 2 Sekunden in einer Messung über 8 Sekunden. Die Spalten `Gen0`, `Gen1` und `Gen2` zeigen die Anzahl der Garbage Collections, die während dieses Intervalls für diese Generation aufgetreten sind.

  ```console
  Interval    Gen0    Gen1    Gen2    % Time in GC
          1       9       3       1              10
          2      10       3       1               1
          3      11       3       1               3
          4      11       3       1               3
  ```

  Diese Informationen geben nicht an, wann die Garbage Collection erfolgt ist, Sie können aber die Anzahl der Garbage Collections ermitteln, die in einem bestimmten Zeitintervall aufgetreten sind. Im schlimmsten Fall wurde die Garbage Collection der zehnten Generation 0 zu Beginn des zweiten Intervalls abgeschlossen und die Garbage Collection der elften Generation 0 zum Ende des fünften Intervalls. Die Zeit zwischen dem Ende der zehnten und dem Ende der elften Garbage Collection ist ungefähr 2 Sekunden, und der Leistungsindikator zeigt 3%. Daher war die Dauer der elften Garbage Collection der Generation 0 (2 Sekunden * 3% = 60ms).

  In diesem Beispiel gibt es 5 Intervalle.

  ```console
  Interval    Gen0    Gen1    Gen2     % Time in GC
          1       9       3       1                3
          2      10       3       1                1
          3      11       4       2                1
          4      11       4       2                1
          5      11       4       2               20
  ```

  Die zweite Garbage Collection der Generation 2 wurde während des dritten Intervalls gestartet und im fünften Intervall abgeschlossen. Im schlimmsten Fall erfolgte die letzte Garbage Collection für eine Collection der Generation 0, die zu Beginn des zweiten Intervalls abgeschlossen wurde, und die Garbage Collection der Generation 2 wurde zum Ende des fünften Intervalls abgeschlossen. Daher ist die Zeit zwischen dem Ende der Garbage Collection der Generation 0 und dem Ende der Garbage Collection der Generation 2 4 Sekunden. Da der `% Time in GC`-Indikator 20% angibt, beträgt die maximale Zeitdauer, die die Garbage Collection der Generation 2 benötigt haben kann: (4 Sekunden * 20% = 800ms).

- Alternativ können Sie die Länge einer Garbage Collection mithilfe der [ETW-Ereignisse der Garbage Collection](../../framework/performance/garbage-collection-etw-events.md) bestimmen und die Informationen analysieren, um so die Dauer der Garbage Collection zu ermitteln.

  Beispielsweise enthalten die folgenden Daten eine Ereignissequenz, die während einer nicht gleichzeitigen Garbage Collection aufgetreten ist.

  ```console
  Timestamp    Event name
  513052        GCSuspendEEBegin_V1
  513078        GCSuspendEEEnd
  513090        GCStart_V1
  517890        GCEnd_V1
  517894        GCHeapStats
  517897        GCRestartEEBegin
  517918        GCRestartEEEnd
  ```

  Das Anhalten des verwalteten Threads dauerte 26us (`GCSuspendEEEnd` - `GCSuspendEEBegin_V1`).

  Die tatsächliche Garbage Collection dauerte 4,8ms (`GCEnd_V1` - `GCStart_V1`).

  Das Fortsetzen der verwalteten Threads dauerte 21us (`GCRestartEEEnd` - `GCRestartEEBegin`).

  Die folgende Ausgabe zeigt ein Beispiel für eine Garbage Collection im Hintergrund und enthält Felder für den Prozess, den Thread und das Ereignis. (Es werden nicht alle Daten gezeigt.)

  ```console
  timestamp(us)    event name            process    thread    event field
  42504385        GCSuspendEEBegin_V1    Test.exe    4372             1
  42504648        GCSuspendEEEnd         Test.exe    4372
  42504816        GCStart_V1             Test.exe    4372        102019
  42504907        GCStart_V1             Test.exe    4372        102020
  42514170        GCEnd_V1               Test.exe    4372
  42514204        GCHeapStats            Test.exe    4372        102020
  42832052        GCRestartEEBegin       Test.exe    4372
  42832136        GCRestartEEEnd         Test.exe    4372
  63685394        GCSuspendEEBegin_V1    Test.exe    4744             6
  63686347        GCSuspendEEEnd         Test.exe    4744
  63784294        GCRestartEEBegin       Test.exe    4744
  63784407        GCRestartEEEnd         Test.exe    4744
  89931423        GCEnd_V1               Test.exe    4372        102019
  89931464        GCHeapStats            Test.exe    4372
  ```

  Das `GCStart_V1`-Ereignis bei 42504816 gibt an, dass dies eine Garbage Collection im Hintergrund ist, da das letzte Feld `1` ist. Dies wird Garbage Collection Nr. 102019.

  Das `GCStart`-Ereignis tritt auf, weil eine kurzlebige Garbage Collection erforderlich ist, bevor eine Garbage Collection im Hintergrund gestartet wird. Dies wird Garbage Collection Nr. 102020.

  Bei 42514170 wird Garbage Collection Nr. 102020 beendet. Die verwalteten Threads werden an diesem Punkt neu gestartet. Dies wird im Thread 4372 abgeschlossen, der diese Garbage Collection im Hintergrund ausgelöst hat.

  Im Thread 4744 tritt eine Unterbrechung auf. Dies ist das einzige Mal, dass die Garbage Collection im Hintergrund verwaltete Threads anhalten muss. Die Dauer beträgt ungefähr 99ms ((63784407-63685394)/1000).

  Das `GCEnd`-Ereignis für die Garbage Collection im Hintergrund wird bei 89931423 angezeigt. Dies bedeutet, dass die Garbage Collection im Hintergrund etwa 47 Sekunden gedauert hat ((89931423-42504816)/1000).

  Während die verwalteten Threads ausgeführt werden, können beliebig viele kurzlebige Garbage Collections stattfinden.

<a name="Triggered"></a>

### <a name="to-determine-what-triggered-a-garbage-collection"></a>So ermitteln Sie, was eine Garbage Collection ausgelöst

- Geben Sie im WinDbg-Debugger oder im Visual Studio-Debugger bei geladener SOS-Debuggererweiterung den folgenden Befehl ein, um alle Threads mit ihren Aufruflisten anzuzeigen:

  **~\*kb**

  Dieser Befehl zeigt eine Ausgabe ähnlich der folgenden an.

  ```console
  0012f3b0 79ff0bf8 mscorwks!WKS::GCHeap::GarbageCollect
  0012f454 30002894 mscorwks!GCInterface::CollectGeneration+0xa4
  0012f490 79fa22bd fragment_ni!request.Main(System.String[])+0x48
  ```

  Wenn die Garbage Collection durch eine Benachrichtigung über unzureichenden Arbeitsspeicher vom Betriebssystem verursacht wurde, sieht die Aufrufliste ähnlich aus, mit dem Unterschied, dass der Thread ein Finalizerthread ist. Der Finalizerthread erhält eine asynchrone Benachrichtigung über unzureichenden Arbeitsspeicher und führt die Garbage Collection aus.

  Wenn die Garbage Collection durch die Speicherbelegung verursacht wurde, sieht der Stapel wie folgt aus:

  ```console
  0012f230 7a07c551 mscorwks!WKS::GCHeap::GarbageCollectGeneration
  0012f2b8 7a07cba8 mscorwks!WKS::gc_heap::try_allocate_more_space+0x1a1
  0012f2d4 7a07cefb mscorwks!WKS::gc_heap::allocate_more_space+0x18
  0012f2f4 7a02a51b mscorwks!WKS::GCHeap::Alloc+0x4b
  0012f310 7a02ae4c mscorwks!Alloc+0x60
  0012f364 7a030e46 mscorwks!FastAllocatePrimitiveArray+0xbd
  0012f424 300027f4 mscorwks!JIT_NewArr1+0x148
  000af70f 3000299f fragment_ni!request..ctor(Int32, Single)+0x20c
  0000002a 79fa22bd fragment_ni!request.Main(System.String[])+0x153
  ```

  Ein Just-In-Time-Hilfsprogramm (`JIT_New*`) ruft schließlich `GCHeap::GarbageCollectGeneration` auf. Wenn Sie feststellen, dass die Garbage Collections der Generation 2 durch Belegungen verursacht werden, müssen Sie ermitteln, welche Objekte von einer Garbage Collection der Generation 2 freigegeben werden und wie sie dies vermeiden können. Das heißt, Sie müssen den Unterschied zwischen dem Anfang und am Ende einer Garbage Collection der Generation 2 sowie die Objekte bestimmen, welche die Collection der Generation 2 verursacht haben.

  Geben Sie beispielsweise den folgenden Befehl im Debugger ein, um den Anfang einer Collection der Generation 2 anzuzeigen:

  **!dumpheap –stat**

  Beispielausgabe (gekürzt, um die Objekte anzuzeigen, die den meisten Platz benötigen):

  ```console
  79124228    31857      9862328 System.Object[]
  035f0384    25668     11601936 Toolkit.TlkPosition
  00155f80    21248     12256296      Free
  79103b6c   297003     13068132 System.Threading.ReaderWriterLock
  7a747ad4   708732     14174640 System.Collections.Specialized.HybridDictionary
  7a747c78   786498     15729960 System.Collections.Specialized.ListDictionary+DictionaryNode
  7a747bac   700298     19608344 System.Collections.Specialized.ListDictionary
  035f0ee4    89192     38887712 Toolkit.TlkOrder
  00fcae40     6193     44911636 WaveBasedStrategy.Tick_Snap[]
  7912c444    91616     71887080 System.Double[]
  791242ec    32451     82462728 System.Collections.Hashtable+bucket[]
  790fa3e0  2459154    112128436 System.String
  Total 6471774 objects
  ```

  Wiederholen Sie den Befehl am Ende der Generation 2:

  **!dumpheap –stat**

  Beispielausgabe (gekürzt, um die Objekte anzuzeigen, die den meisten Platz benötigen):

  ```console
  79124228    26648      9314256 System.Object[]
  035f0384    25668     11601936 Toolkit.TlkPosition
  79103b6c   296770     13057880 System.Threading.ReaderWriterLock
  7a747ad4   708730     14174600 System.Collections.Specialized.HybridDictionary
  7a747c78   786497     15729940 System.Collections.Specialized.ListDictionary+DictionaryNode
  7a747bac   700298     19608344 System.Collections.Specialized.ListDictionary
  00155f80    13806     34007212      Free
  035f0ee4    89187     38885532 Toolkit.TlkOrder
  00fcae40     6193     44911636 WaveBasedStrategy.Tick_Snap[]
  791242ec    32370     82359768 System.Collections.Hashtable+bucket[]
  790fa3e0  2440020    111341808 System.String
  Total 6417525 objects
  ```

  Die `double[]`-Objekte am Ende der Ausgabe sind verschwunden, das heißt, sie wurden freigegeben. Diese Objekte umfassen etwa 70 MB. Bei den übrigen Objekten gab es kaum Änderungen. Daher waren diese `double[]`-Objekte der Grund, weshalb diese Garbage Collection der Generation 2 ausgeführt wurde. Der nächster Schritt besteht darin, zu bestimmen, warum die `double[]`-Objekte vorhanden sind und warum sie inaktiv waren. Sie können den Codeentwickler fragen, woher diese Objekte stammen, oder Sie können den Befehl **gcroot** verwenden.

<a name="HighCPU"></a>

### <a name="to-determine-whether-high-cpu-usage-is-caused-by-garbage-collection"></a>So ermitteln Sie, ob die hohe CPU-Auslastung durch die Garbage Collection verursacht wird

- Setzen Sie den Wert des Speicherleistungsindikators `% Time in GC` zur Prozesszeit in Beziehung.

  Wenn der `% Time in GC`-Wert zum selben Zeitpunkt einen Spitzenwert erreicht wie die Prozesszeit, dann verursacht die Garbage Collection die hohe CPU-Auslastung. Erstellen Sie andernfalls ein Profil der Anwendung, um zu ermitteln, wie die hohe Auslastung zustande kommt.

## <a name="see-also"></a>Siehe auch

- [Garbage Collection](index.md)
