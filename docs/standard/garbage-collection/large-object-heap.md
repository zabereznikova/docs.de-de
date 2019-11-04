---
title: Der große Objektheap auf Windows-Systemen
ms.date: 05/02/2018
helpviewer_keywords:
- large object heap (LOH)"
- LOH
- garbage collection, large object heap
- GC [.NET ], large object heap
ms.openlocfilehash: 618db9faff137e6ff0f878c928e3a889cff37838
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120934"
---
# <a name="the-large-object-heap-on-windows-systems"></a>Der große Objektheap auf Windows-Systemen

Der .NET Garbage Collector (GC) teilt Objekte in die Kategorie „klein“ oder „groß“ ein. Wenn ein Objekt groß ist, sind einige seiner Attribute wichtiger als bei einem kleinen Objekt. Die Komprimierung, also das Kopieren in den Arbeitsspeicher an einer anderen Stelle des Heaps, kann aufwändig sein. Deshalb platziert der .NET Garbage Collector große Objekte im großen Objektheap (Large Object Heap, LOB). In diesem Artikel wird der große Objektheap näher erläutert. Es wird erläutert, wodurch ein Objekt als großes Objekt angesehen wird, wie diese großen Objekte bereinigt werden und in welcher Weise sich große Objekte auf die Leistung auswirken.

> [!IMPORTANT]
> In diesem Artikel wird der große Objektheap in .NET Framework und .NET Core auf Windows-Systemen erläutert. Der große Objektheap in .NET-Implementierungen auf anderen Plattformen wird nicht behandelt.

## <a name="how-an-object-ends-up-on-the-large-object-heap-and-how-gc-handles-them"></a>Wie ein Objekt in den großen Objektheap gelangt und wie der Garbage Collector dieses verarbeitet

Ein Objekt wird als großes Objekt betrachtet, wenn es eine Größe von mindestens 85.000 Byte aufweist. Diese Zahl wurde von der Leistungsoptimierung ermittelt. Wenn die Zuordnungsanforderung für ein Objekt über 85.000 Byte beträgt, ordnet die Runtime diese dem großen Objektheap zu.

Im Folgenden werden einige Grundlagen über den .NET Garbage Collector erläutert, um dies besser nachvollziehen zu können.

Der .NET Garbage Collector ein generationsbasierter Collector. Er verfügt über drei Generationen: Generation 0, Generation 1 und Generation 2. Es gibt drei Generationen, da in einer gut eingerichteten App die meisten Objekte in Generation 0 inaktiv werden. In einer Server-App sollten die Zuordnungen für jede Anforderung inaktiv werden, nachdem die Anforderung abgeschlossen wurde. Die noch nicht abgeschlossenen Zuordnungsanforderungen gelangen in Generation 1 und werden dann inaktiv. Im Grunde dient Generation 1 als Puffer zwischen Bereichen mit neuen Objekten und Bereichen mit langlebigen Objekten.

Kleine Objekte werden immer in Generation 0 zugeordnet und je nach Lebensdauer entweder in Generation 1 oder 2 heraufgestuft. Große Objekte werden immer in Generation 2 zugeordnet.

Große Objekte gehören zu Generation 2, da sie nur während einer Garbage Collection für Generation 2 bereinigt werden. Wenn eine Generation bereinigt wird, werden alle jüngeren Generationen ebenfalls bereinigt. So findet beispielsweise bei einer Garbage Collection für Generation 1 eine Bereinigung der Generationen 1 und 0 statt. Erfolgt eine Garbage Collection für Generation 2, wird der gesamte Heap bereinigt. Aus diesem Grund wird eine Garbage Collection für Generation 2 auch als *vollständige Garbage Collection* bezeichnet. In diesem Artikel wird „Garbage Collection für Generation 2“ statt „vollständige Garbage Collection“ verwendet, die Begriffe sind jedoch synonym.

Die Generationen stellen eine logische Ansicht des Garbage Collection-Heaps bereit. Physisch gesehen werden Objekte in verwalteten Heapsegmenten gespeichert. Ein *verwaltetes Heapsegment* ist ein Speicherblock, den der Garbage Collector vom Betriebssystem (durch Aufrufen der [VirtualAlloc-Funktion](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc)) für verwalteten Code reserviert. Beim Laden der CLR ordnet der Garbage Collector zunächst zwei Heapsegmente zu: eines für kleine Objekte (der kleine Objektheap) und eines für große Objekte (der große Objektheap).

Die Zuordnungsanforderungen werden dann erfüllt, indem verwaltete Objekte in diesen verwalteten Heapsegmenten abgelegt werden. Wenn das Objekt kleiner als 85.000 Byte ist, wird es im Segment für den kleinen Objektheap abgelegt, andernfalls im Segment für einen großen Objektheap. Segmente werden (in kleineren Blöcken) übernommen, wenn ihnen immer mehr Objekte zugeordnet werden.
Beim kleinen Objektheap werden Objekte, die bei einer Garbage Collection nicht bereinigt werden, in die nächste Generation heraufgestuft. Objekte, die in einer Garbage Collection für Generation 0 nicht bereinigt werden, werden nun als Objekte von Generation 1 betrachtet und so weiter. Objekte, die die älteste Generation überdauern, werden jedoch weiterhin als Objekte der ältesten Generation betrachtet. Die Objekte, die Generation 2 überdauern, sind also Objekte von Generation 2, und die Objekte, die den großen Objektheap überdauern, sind Objekte des großen Objektheaps (die in Generation 2 bereinigt werden).

Benutzercode kann nur in der Generation 0 (kleine Objekte) oder im großen Objektheap (große Objekte) zugeordnet werden. Nur der Garbage Collector kann Objekte von Generation 1 (durch Heraufstufen beibehaltener Objekte aus Generation 0) und Generation 2 (durch Heraufstufen beibehaltener Objekte aus den Generationen 1 und 2) zuordnen.

Wenn eine Garbage Collection ausgelöst wird, geht der Garbage Collector alle aktiven Objekte durch und komprimiert sie. Da die Komprimierung jedoch aufwändig ist, *bereinigt* die Garbage Collection den großen Objektheap. Dabei wird eine Freiliste aus inaktiven Objekten erstellt, die später zur Erfüllung von Zuordnungsanforderungen für große Objekte wiederverwendet werden kann. Angrenzende inaktive Objekte werden in ein einzelnes freies Objekt umgewandelt.

.NET Core und .NET Framework (ab .NET Framework 4.5.1) enthalten die <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode?displayProperty=nameWithType>-Eigenschaft, durch die Benutzer angegeben können, dass der große Objektheap während der nächsten vollständigen blockierenden Garbage Collection komprimiert werden soll. Zukünftig erfolgt die Komprimierung des großen Objektheaps in .NET möglicherweise automatisch. Daher sollten Sie diese Objekte fixieren, wenn Sie große Objekte zuordnen und sicherstellen möchten, dass diese nicht verschoben werden.

Abbildung 1 zeigt ein Szenario, bei dem Generation 1 nach der ersten Garbage Collection für Generation 0 gebildet wird, bei der `Obj1` und `Obj3` inaktiv sind. Generation 2 wird nach der ersten Garbage Collection für Generation 1 gebildet, bei der `Obj2` und `Obj5` inaktiv sind. Beachten Sie, dass diese und die folgenden Abbildungen nur zur Veranschaulichung dienen. Sie enthalten nur wenige Objekte, um besser darzustellen, was auf dem Heap geschieht. In der Praxis sind an einer Garbage Collection in der Regel wesentlich mehr Objekte beteiligt.

![Abbildung 1: Garbage Collection für Generation 0 und 1](media/loh/loh-figure-1.jpg)\
Abbildung 1: Garbage Collection für Generation 0 und 1.

Abbildung 2 veranschaulicht, dass nach einer Garbage Collection für Generation 2, bei der `Obj1` und `Obj2` inaktiv sind, bildet die Garbage Collection freien Arbeitsspeicher, der von `Obj1` und `Obj2` belegt werden kann. Diese werden dann verwendet, um eine Zuordnungsanforderung für `Obj4` zu erfüllen. Der Speicherplatz nach dem letzten Objekt (`Obj3`) bis zum Ende des Segments kann ebenfalls zur Erfüllung von Zuordnungsanforderungen verwendet werden.

![Abbildung 2: Nach einer Garbage Collection für Generation 2](media/loh/loh-figure-2.jpg)\
Abbildung 2: Nach einer Garbage Collection für Generation 2

Wenn nicht genügend Speicherplatz zur Erfüllung der Zuordnungsanforderungen für große Objekte verfügbar ist, versucht die Garbage Collection zunächst, weitere Segmente vom Betriebssystem anzufordern. Wenn dies fehlschlägt, wird eine Garbage Collection für Generation 2 ausgelöst, um Speicherplatz freizugeben.

Bei einer Garbage Collection für Generation 1 oder 2 gibt der Garbage Collector Segmente frei für das Betriebssystem, in denen keine aktiven Objekte vorhanden sind, indem die Funktion [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree) aufgerufen wird. Der Speicherplatz nach dem letzten aktiven Objekt bis zum Ende des Segments wird aufgehoben (außer in dem kurzlebigen Segment, in dem Generation 0 und Generation 1 aktiv sind und in dem der Garbage Collector einigen Speicherplatz beibehält, da dieser sofort Ihrer Anwendung zugewiesen wird). Die freien Speicherblöcke sind nach wie vor committet, obwohl sie zurückgesetzt werden. Das bedeutet, dass das Betriebssystem in ihnen befindliche Daten nicht wieder auf den Datenträger schreiben muss.

Da der große Objektheap nur während Garbage Collections für Generation 2 bereinigt wird, kann ein Segment des großen Objektheaps nur während einer solchen Garbage Collection freigegeben werden. In Abbildung 3 wird ein Szenario veranschaulicht, indem der Garbage Collector ein Segment (Segment 2) für das Betriebssystem freigibt und mehr Speicherplatz für die verbleibenden Segmente aufhebt. Wenn der aufgehobene Speicherplatz am Ende des Segments verwendet werden muss, um Zuordnungsanforderungen für große Objekte zu erfüllen, wird der Arbeitsspeicher wieder committet. (Eine Erläuterung zum Übernehmen und Aufheben finden Sie in der Dokumentation für [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc).)

![Abbildung 3: Großer Objektheap nach einer Garbage Collection für Generation 2](media/loh/loh-figure-3.jpg)\
Abbildung 3: Der große Objektheap nach einer Garbage Collection für Generation 2

## <a name="when-is-a-large-object-collected"></a>Wann wird ein großes Objekt bereinigt?

Im Allgemeinen wird eine Garbage Collection durchgeführt, wenn eine der folgenden drei Bedingungen zutrifft:

- Die Zuordnung überschreitet den Schwellenwert von Generation 0 oder des großen Objekts.

  Der Schwellenwert ist eine Eigenschaft einer Generation. Ein Schwellenwert wird für eine Generation festgelegt, wenn der Garbage Collector diesem Objekte zuordnet. Wenn der Schwellenwert überschritten wird, wird eine Garbage Collection für diese Generation ausgelöst. Wenn Sie kleine oder große Objekte zuweisen, verwenden Sie daher die jeweiligen Schwellenwerte für Generation 0 und den großen Objektheap. Wenn der Garbage Collector eine Zuordnung zu Generation 1 oder 2 vornimmt, verwendet er deren Schwellenwerte. Diese Schwellenwerte werden während der Ausführung des Programms dynamisch abgestimmt.

  Dies ist der Normalfall. Die meisten Garbage Collections werden aufgrund von Zuordnungen im verwalteten Heap ausgelöst.

- Die <xref:System.GC.Collect%2A?displayProperty=nameWithType> -Methode wird aufgerufen.

  Wenn die parameterlose <xref:System.GC.Collect?displayProperty=nameWithType>-Methode aufgerufen wird oder eine andere Überladung als Argument an <xref:System.GC.MaxGeneration?displayProperty=nameWithType> übergeben wird, wird der große Objektheap zusammen mit dem restlichen verwalteten Heap bereinigt.

- Das System verfügt über wenig Arbeitsspeicher.

  Dies tritt auf, wenn der Garbage Collector eine Benachrichtigung über eine hohe Arbeitsspeicherauslastung vom Betriebssystem erhält. Wenn der Garbage Collector eine Garbage Collection für Generation 2 für produktiv hält, wird diese ausgelöst.

## <a name="loh-performance-implications"></a>Auswirkungen des großen Objektheaps auf die Leistung

Zuordnungen zum großen Objektheap beeinträchtigen die Leistung folgendermaßen:

- Zuordnungskosten:

  Die CLR garantiert, dass der Speicher für jedes neue Objekt, das herausgegeben wird, bereinigt wird. Dies bedeutet, dass die Zuordnungskosten für ein großes Objekt vollständig von der Speicherbereinigung dominiert werden (sofern keine Garbage Collection ausgelöst wird). Wenn zwei Zyklen für die Bereinigung von einem Byte benötigt werden, bedeutet dies, dass zum Bereinigen des kleinsten großen Objekts 170.000 Zyklen erforderlich sind. Das Bereinigen des Arbeitsspeichers eines 16 MB großen Objekts auf einem Computer mit 2 GHz dauert ungefähr 16 Millisekunden. Dies führt zu hohen Kosten.

- Bereinigungskosten:

  Da der große Objektheap und Generation 2 zusammen bereinigt werden, wird eine Garbage Collection für Generation 2 ausgelöst, wenn einer der beiden Schwellenwerte überschritten wird. Wenn eine Garbage Collection für Generation 2 aufgrund des großen Objektheaps ausgelöst wurde, wird Generation 2 nach der Garbage Collection nicht unbedingt erheblich kleiner. Wenn nicht viele Daten zu Generation 2 gehören, hat dies nur minimale Auswirkungen. Ist Generation 2 jedoch groß, können Leistungsprobleme auftreten, wenn viele Garbage Collections für Generation 2 ausgelöst werden. Wenn viele große Objekte nur vorübergehend zugewiesen werden und Sie über einen großen kleinen Objektheap verfügen, verwenden Sie möglicherweise zu viel Zeit für Garbage Collections. Darüber hinaus können die Zuordnungskosten sich summieren, wenn Sie sehr große Objekte weiterhin zuordnen und freigeben.

- Arrayelemente mit Verweistypen:

  Sehr große Objekte im großen Objektheap sind in der Regel Arrays (es kommt äußerst selten vor, dass ein sehr großes Instanzobjekt vorhanden ist). Wenn die Elemente eines Arrays viele Verweise enthalten, fallen Kosten an, die bei Elementen mit wenigen Verweise nicht anfallen. Enthält das Element keine Verweise, muss der Garbage Collector das Array überhaupt nicht durchlaufen. Wenn Sie beispielsweise ein Array zum Speichern von Knoten in einer binären Struktur verwenden, könnte dies implementiert werden, indem durch die tatsächlichen Knoten auf den rechten und linken Knoten eines Knotens verwiesen wird:

  ```csharp
  class Node
  {
     Data d;
     Node left;
     Node right;
  };

  Node[] binary_tr = new Node [num_nodes];
  ```

  Wenn `num_nodes` groß ist, muss der Garbage Collector mindestens zwei Verweise pro Element durchlaufen. Ein alternativer Ansatz besteht darin, den Index des rechten und des linken Knotens zu speichern:

  ```csharp
  class Node
  {
     Data d;
     uint left_index;
     uint right_index;
  } ;
  ```

  Verweisen Sie auf die Daten des linken Knotens nicht mit `left.d`, sondern mit `binary_tr[left_index].d`. Der Garbage Collector muss dann keine Verweise für den linken und rechten Knoten betrachten.

Von diesen drei Faktoren sind die ersten beiden üblicherweise relevanter als der dritte. Deshalb wird empfohlen, dass Sie einen Pool von großen Objekten zuordnen, den Sie wiederverwenden, statt temporäre Objekte zuzuordnen.

## <a name="collecting-performance-data-for-the-loh"></a>Sammeln von Leistungsdaten für den großen Objektheap

Bevor Sie Leistungsdaten für einen bestimmten Bereich erfassen, sollten Sie Folgendes durchgeführt haben:

1. Beweise dafür suchen, dass Sie diesen Bereich überprüfen sollten

2. Andere bekannte Bereiche ohne ein Ergebnis untersuchen, das das vorhandene Leistungsproblem erklären könnte

Weitere Informationen zu den Grundlagen zu Arbeitsspeicher und CPU finden Sie im Blogbeitrag [Understand the problem before you try to find a solution (Verstehen des Problems vor der Lösungsfindung)](https://devblogs.microsoft.com/dotnet/understand-the-problem-before-you-try-to-find-a-solution/).

Sie können folgende Tools verwenden, um Daten über die Leistung des großen Objektheaps zu erfassen:

- [.NET CLR-Speicherleistungsindikatoren](#net-clr-memory-performance-counters)

- [ETW-Ereignisse](#etw-events)

- [Debugger](#a-debugger)

### <a name="net-clr-memory-performance-counters"></a>.NET CLR-Speicherleistungsindikatoren

Diese Speicherleistungsindikatoren sind in der Regel ein guter erster Schritt bei der Untersuchung von Leistungsproblemen. Es wird jedoch empfohlen, [ETW-Ereignisse](#etw-events) zu verwenden. Sie können den Systemmonitor wie in Abbildung 4 dargestellt konfigurieren, indem Sie die gewünschten Indikatoren hinzufügen. Folgende sind für den großen Objektheap relevant:

- **Anzahl der Garbage Collections für Generation 2**

   Zeigt an, wie viele Garbage Collections für Generation 2 durchgeführt wurden, seit der Prozess gestartet wurde. Der Indikator wird am Ende einer Garbage Collection für Generation 2 (auch als vollständige Garbage Collection bezeichnet) erhöht. Dieser Indikator zeigt den letzten erfassten Wert an.

- **Größe des Heap für große Objekte**

   Zeigt die aktuelle Größe des großen Objektheaps in Byte (einschließlich des freien Speicherplatzes) an. Dieser Indikator wird nicht bei jeder Zuordnung, sondern nur am Ende einer Garbage Collection aktualisiert.

Eine allgemeine Möglichkeit zum Anzeigen von Leistungsindikatoren ist die Verwendung des Systemmonitors (perfmon.exe). Fügen Sie den entsprechenden Indikator für Prozesse, die für Sie wichtig sind, mithilfe von „Leistungsindikatoren hinzufügen“ hinzu. Sie können die Leistungsindikatordaten im Systemmonitor wie in Abbildung 4 dargestellt in einer Protokolldatei speichern:

![Screenshot zeigt Hinzufügen von Leistungsindikatoren.](media/large-object-heap/add-performance-counter.png)
Abbildung 4: Der große Objektheap nach einer Garbage Collection für Generation 2

Leistungsindikatoren können auch programmgesteuert abgefragt werden. Viele Benutzer sammeln die Leistungsdaten auf diese Weise im Rahmen ihrer alltäglichen Testprozesse. Wenn Indikatoren mit ungewöhnlichen Werten angezeigt werden, können dann mithilfe anderer Methoden detailliertere Daten abgerufen werden, um die Untersuchung zu erleichtern.

> [!NOTE]
> Es wird empfohlen, ETW-Ereignisse statt Leistungsindikatoren zu verwenden, da ETW umfangreichere Informationen bereitstellt.

### <a name="etw-events"></a>ETW-Ereignisse

Der Garbage Collector bietet viele ETW-Ereignisse, mit denen Sie besser nachvollziehen können, welche Aktionen der Heap durchführt und warum. In folgenden Blogbeiträgen wird das Erfassen und Verstehen von GC-Ereignissen mit ETW veranschaulicht:

- [GC ETW Events - 1 (Garbage Collection: ETW-Ereignisse (1))](https://devblogs.microsoft.com/dotnet/gc-etw-events-1/)

- [GC ETW Events - 2 (Garbage Collection: ETW-Ereignisse (2))](https://devblogs.microsoft.com/dotnet/gc-etw-events-2/)

- [GC ETW Events - 3 (Garbage Collection: ETW-Ereignisse (3))](https://devblogs.microsoft.com/dotnet/gc-etw-events-3/)

- [GC ETW Events - 4 (Garbage Collection: ETW-Ereignisse (4))](https://devblogs.microsoft.com/dotnet/gc-etw-events-4/)

Betrachten Sie die Spalte „Triggergrund“ für die Garbage Collections, um übermäßige Garbage Collections für Generation 2 zu identifizieren, die von temporären Zuordnungen von großen Objektheaps verursacht wurden. Wenn Sie einen einfachen Test durchführen möchten, der nur große Objekte temporär zuordnet, können Sie mithilfe der folgenden [PerfView](https://www.microsoft.com/download/details.aspx?id=28567)-Befehlszeile Informationen zu ETW-Ereignissen erfassen:

```console
perfview /GCCollectOnly /AcceptEULA /nogui collect
```

Das Ergebnis ähnelt Folgendem:

![Screenshot mit ETW-Ereignissen in PerfView.](media/large-object-heap/event-tracing-windows-perfview.png)
Abbildung 5: Mithilfe von PerfView angezeigte ETW-Ereignisse

Sie werden feststellen, dass alle Garbage Collections für Generation 2 durchgeführt und von AllocLarge ausgelöst wurden. Das bedeutet, dass die Zuordnung eines großen Objekts diese Garbage Collection ausgelöst hat. Es ist bekannt, dass es sich um temporäre Zuordnungen handelt, da die Spalte **LOH Survival Rate** (Beibehaltungsrate des großen Objektheaps) „1 %“ anzeigt.

Sie können zusätzliche ETW-Ereignisse erfassen, aus denen hervorgeht, wer diese großen Objekte zugeordnet hat. Verwenden Sie beispielsweise folgende Befehlszeile:

```console
perfview /GCOnly /AcceptEULA /nogui collect
```

Dadurch wird ein AllocationTick-Ereignis erfasst, das etwa alle 100.000 Zuordnungen ausgelöst wird. Das bedeutet, dass immer dann ein Ereignis ausgelöst wird, wenn ein großes Objekt zugeordnet wird. Sie können dann eine der Ansichten für die Heapzuordnung der Garbage Collection betrachten, in denen die Aufruflisten angezeigt werden, die große Objekte zugeordnet haben:

![Screenshot mit Garbage Collector Heap-Ansicht.](media/large-object-heap/garbage-collector-heap.png)
Abbildung 6: Ansicht der Heapzuordnung einer Garbage Collection

Wie Sie sehen können, handelt es sich hierbei um einen einfachen Test, der nur große Objekte aus seiner `Main`-Methode zuordnet.

### <a name="a-debugger"></a>Debugger

Wenn Sie nur ein Speicherabbild besitzen und untersuchen müssen, welche Objekte sich im großen Objektheap befinden, können Sie die von .NET bereitgestellte [SOS-Debugerweiterung](../../../docs/framework/tools/sos-dll-sos-debugging-extension.md) verwenden.

> [!NOTE]
> Die in diesem Abschnitt erwähnten Debuggingbefehle gelten für die [Windows-Debugger](https://www.microsoft.com/whdc/devtools/debugging/default.mspx).

Nachfolgend wird eine Beispielausgabe für die Analyse des großen Objektheaps angezeigt:

```console
0:003> .loadby sos mscorwks
0:003> !eeheap -gc
Number of GC Heaps: 1
generation 0 starts at 0x013e35ec
sdgeneration 1 starts at 0x013e1b6c
generation 2 starts at 0x013e1000
ephemeral segment allocation context: none
segment   begin allocated     size
0018f2d0 790d5588 790f4b38 0x0001f5b0(128432)
013e0000 013e1000 013e35f8 0x000025f8(9720)
Large object heap starts at 0x023e1000
segment   begin allocated     size
023e0000 023e1000 033db630 0x00ffa630(16754224)
033e0000 033e1000 043cdf98 0x00fecf98(16699288)
043e0000 043e1000 05368b58 0x00f87b58(16284504)
Total Size 0x2f90cc8(49876168)
------------------------------
GC Heap Size 0x2f90cc8(49876168)
0:003> !dumpheap -stat 023e1000 033db630
total 133 objects
Statistics:
MT   Count   TotalSize Class Name
001521d0       66     2081792     Free
7912273c       63     6663696 System.Byte[]
7912254c       4     8008736 System.Object[]
Total 133 objects
```

Die Größe des großen Objektheaps beträgt 49.738.016 Byte (16.754.224 + 16.699.288 + 16.284.504). Zwischen den Adressen 023e1000 und 033db630 sind 8.008.736 Byte von einem Array von <xref:System.Object?displayProperty=nameWithType>-Objekten und 6.663.696 Byte sind von einem Array von <xref:System.Byte?displayProperty=nameWithType>-Objekten belegt. 2.081.792 Byte sind von freiem Speicherplatz belegt.

Manchmal zeigt der Debugger an, dass die Gesamtgröße des großen Objektheaps weniger als 85.000 Byte beträgt. Dies geschieht, weil die Runtime den großen Objektheap zur Zuordnung von bestimmten Objekten verwendet, die kleiner als ein großes Objekt sind.

Da der große Objektheap nicht komprimiert wird, wird der große Objektheap manchmal für die Quelle der Fragmentierung gehalten. Fragmentierung bedeutet:

- Die Fragmentierung des verwalteten Heaps, die sich durch die Menge des freien Speicherplatzes zwischen verwalteten Objekten auszeichnet. Im SOS-Debugger zeigt der `!dumpheap –type Free`-Befehl die Menge des freien Speicherplatzes zwischen verwalteten Objekten an.

- Die Fragmentierung des Adressraums des virtuellen Arbeitsspeichers, bei dem es sich um den Arbeitsspeicher handelt, der als `MEM_FREE` markiert ist. Sie können diesen mithilfe von verschiedenen Debuggerbefehlen in WinDbg abrufen.

   Im folgenden Beispiel wird die Fragmentierung des virtuellen Arbeitsspeichers dargestellt:

   ```console
   0:000> !address
   00000000 : 00000000 - 00010000
   Type     00000000
   Protect 00000001 PAGE_NOACCESS
   State   00010000 MEM_FREE
   Usage   RegionUsageFree
   00010000 : 00010000 - 00002000
   Type     00020000 MEM_PRIVATE
   Protect 00000004 PAGE_READWRITE
   State   00001000 MEM_COMMIT
   Usage   RegionUsageEnvironmentBlock
   00012000 : 00012000 - 0000e000
   Type     00000000
   Protect 00000001 PAGE_NOACCESS
   State   00010000 MEM_FREE
   Usage   RegionUsageFree
   … [omitted]
   -------------------- Usage SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Pct(Busy)   Usage
   701000 (   7172) : 00.34%   20.69%   : RegionUsageIsVAD
   7de15000 ( 2062420) : 98.35%   00.00%   : RegionUsageFree
   1452000 (   20808) : 00.99%   60.02%   : RegionUsageImage
   300000 (   3072) : 00.15%   08.86%   : RegionUsageStack
   3000 (     12) : 00.00%   00.03%   : RegionUsageTeb
   381000 (   3588) : 00.17%   10.35%   : RegionUsageHeap
   0 (       0) : 00.00%   00.00%   : RegionUsagePageHeap
   1000 (       4) : 00.00%   00.01%   : RegionUsagePeb
   1000 (       4) : 00.00%   00.01%   : RegionUsageProcessParametrs
   2000 (       8) : 00.00%   00.02%   : RegionUsageEnvironmentBlock
   Tot: 7fff0000 (2097088 KB) Busy: 021db000 (34668 KB)

   -------------------- Type SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Usage
   7de15000 ( 2062420) : 98.35%   : <free>
   1452000 (   20808) : 00.99%   : MEM_IMAGE
   69f000 (   6780) : 00.32%   : MEM_MAPPED
   6ea000 (   7080) : 00.34%   : MEM_PRIVATE

   -------------------- State SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Usage
   1a58000 (   26976) : 01.29%   : MEM_COMMIT
   7de15000 ( 2062420) : 98.35%   : MEM_FREE
   783000 (   7692) : 00.37%   : MEM_RESERVE

   Largest free region: Base 01432000 - Size 707ee000 (1843128 KB)
   ```

Häufiger kommt es vor, dass eine Fragmentierung des virtuellen Arbeitsspeichers durch temporäre große Objekte verursacht wird, für die erforderlich ist, dass der Garbage Collector regelmäßig neue verwaltete Heapsegmente vom Betriebssystem abruft und leere Segmente wieder für das Betriebssystem freigibt.

Sie können überprüfen, ob der große Objektheap die Fragmentierung des virtuellen Arbeitsspeichers verursacht, indem Sie einen Haltepunkt für [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) und [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree) festlegen und bestimmen, von wem diese Funktionen aufgerufen werden. Sie können einen Breakpoint z.B. folgendermaßen festlegen, um anzuzeigen, wer versucht hat, virtuelle Arbeitsspeicherblöcke, die größer als 8 MB sind, aus dem Betriebssystem zuzuordnen:

```console
bp kernel32!virtualalloc "j (dwo(@esp+8)>800000) 'kb';'g'"
```

Dieser Befehl unterbricht den Debugger und zeigt die Aufrufliste nur an, wenn [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) mit einer Zuordnungsgröße aufgerufen wird, die größer als 8 MB (0x800000) ist.

In CLR 2.0 wurde ein Feature namens *VM Hoarding* hinzugefügt, das für Szenarios nützlich ist, in denen Segmente (einschließlich des großen und des kleinen Objektheaps) häufig abgerufen und freigegeben werden. Wenn Sie das Feature „VM Hoarding“ definieren möchten, geben Sie ein Startflag namens `STARTUP_HOARD_GC_VM` über die Hosting-API an. Die CLR hebt den Arbeitsspeicher für diese Segmente auf, und setzt diese auf eine Standbyliste, anstatt leere Segmente wieder für das Betriebssystem freizugeben. (Beachten Sie, dass die CLR dies nicht für Segmente durchführen kann, die zu groß sind.) Die CLR verwendet diese Segmente später, um Anforderungen für neue Segmente zu erfüllen. Wenn Ihre App das nächste Mal ein neues Segment benötigt, verwendet die CLR eines von dieser Standbyliste, wenn sie eines finden kann, das groß genug ist.

Das Feature „VM Hoarding“ ist ebenfalls für Anwendungen nützlich, die Segmente beibehalten möchten, die bereits abgerufen wurden. Dazu zählen beispielsweise Server-Apps, die als dominante Apps auf dem System ausgeführt werden, um die Ausnahme „Nicht genügend Arbeitsspeicher.“ zu vermeiden.

Es wird nachdrücklich empfohlen, dass Sie Ihre Anwendung sorgfältig testen, wenn Sie dieses Feature verwenden, und sicherstellen, dass die Speicherauslastung Ihrer Anwendung relativ stabil ist.
