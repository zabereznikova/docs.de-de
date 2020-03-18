---
title: Grundlagen der Garbage Collection
description: Erfahren Sie, wie der Garbage Collector funktioniert und wie er für eine optimale Leistung konfiguriert werden kann.
ms.date: 11/15/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, generations
- garbage collection, background
- garbage collection, concurrent
- garbage collection, server
- garbage collection, workstation
- garbage collection, managed heap
ms.assetid: 67c5a20d-1be1-4ea7-8a9a-92b0b08658d2
ms.openlocfilehash: ea8aef03d2f5837f35ecb31209e57853c0c8257b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398544"
---
# <a name="fundamentals-of-garbage-collection"></a>Grundlagen der Garbage Collection

In der Common Language Runtime (CLR) dient der Garbage Collector (GC) als automatischer Speicher-Manager. Der Garbage Collector bietet folgende Vorteile:

- Ermöglicht es Ihnen, eine Anwendung zu entwickeln, ohne den Speicher manuell freigeben zu müssen.

- Ordnet dem verwalteten Heap effizient Objekte zu.

- Gibt Objekte frei, die nicht mehr verwendet werden, löscht den Speicher und hält Speicher für zukünftige Belegungen bereit. Verwaltete Objekte beginnen automatisch mit einem bereinigten Inhalt, damit ihre Konstruktoren nicht jedes Datenfeld initialisieren müssen.

- Bietet Speichersicherheit, indem sichergestellt wird, dass ein Objekt den Inhalt eines anderen Objekts nicht verwenden kann.

In diesem Artikel werden die wichtigsten Konzepte der Garbage Collection beschrieben.

## <a name="fundamentals-of-memory"></a>Grundlagen des Arbeitsspeichers

Die folgende Liste liefert eine Zusammenfassung wichtiger Arbeitsspeicherkonzepte der CLR.

- Jeder Prozess verfügt über einen eigenen separaten virtuellen Adressraum. Alle Prozesse auf demselben Computer verwenden den gleichen physischen Speicher und die gleiche Auslagerungsdatei, sofern vorhanden.

- In der Standardeinstellung verfügt jeder Prozess auf 32-Bit-Computern über einen virtuellen Adressraum von 2 GB im Benutzermodus.

- Als Anwendungsentwickler arbeiten Sie immer mit einem virtuellem Adressraum und manipulieren niemals direkt den physischen Speicher. Der Garbage Collector belegt und gibt virtuellen Arbeitsspeicher auf dem verwalteten Heap frei.

  Wenn Sie nativen Code schreiben, verwenden Sie die Windows-Funktionen für das Arbeiten mit dem virtuellen Adressraum. Diese Funktionen belegen und geben für Sie virtuellen Arbeitsspeicher auf systemeigenen Heaps frei.

- Virtueller Arbeitsspeicher kann sich in einem von drei Zuständen befinden:

  - Frei. Es sind keine Verweise auf den Speicherblock vorhanden, und der Speicherblock ist für eine Speicherbelegung verfügbar.

  - Reserviert. Der Speicherblock ist für die Verwendung verfügbar und kann nicht durch andere Anforderungen belegt werden. Sie können jedoch keine Daten in diesem Speicherblock speichern, bis eine Zusicherung erfolgt ist.

  - Zugesichert. Der Speicherblock ist einem physischen Speicher zugewiesen.

- Im virtuellen Adressraum können Fragmentierungen auftreten. Das bedeutet, dass freie Blöcke (Lücken) im Adressraum vorhanden sind. Wenn eine virtuelle Speicherbelegung angefordert wird, muss der Manager für virtuellen Arbeitsspeicher einen einzelnen freien Block finden, der groß genug ist, um die Belegungsanforderung zu erfüllen. Selbst wenn 2 GB freier Speicherplatz verfügbar sind, wird die Speicherbelegung, die 2 GB angefordert hat, fehlschlagen, wenn der freie Speicherplatz nicht in einem einzelnen Adressblock verfügbar ist.

- Es kann vorkommen, dass nicht mehr genügend Arbeitsspeicher zur Verfügung steht, weil der für Belegungen verfügbare virtuelle Adressraum oder der für Zusicherungen verfügbare physische Speicher nicht mehr ausreicht.

  Die Auslagerungsdatei wird auch dann verwendet, wenn der tatsächliche physische Speicherbedarf insgesamt eher niedrig ist. Wenn das erste Mal eine hohe physische Speicherauslastung auftritt, muss das Betriebssystem im physischen Speicher freien Platz für die Datenspeicherung schaffen. Zu diesem Zweck werden einige Daten aus dem physischen Speicher in die Auslagerungsdatei verschoben. Für diese Daten erfolgt solange keine neue Speicherzuordnung, bis sie tatsächlich benötigt werden. Daher können Situationen entstehen, in denen auch bei einer geringen physischen Speicherauslastung Daten in der Auslagerungsdatei abgelegt sind.

## <a name="conditions-for-a-garbage-collection"></a>Bedingungen für eine Garbage Collection

Eine Garbage Collection wird durchgeführt, wenn eine der folgenden Bedingungen zutrifft:

- Das System verfügt über einen kleinen physikalischen Speicher. Dies wird entweder durch die Meldung des Betriebssystems über zu wenig Arbeitsspeicher oder durch die Meldung des Hosts über zu wenig Arbeitsspeicher erkannt.

- Der Speicher, der von Objekten belegt wird, die dem verwalteten Heap zugeordnet sind, übersteigt einen akzeptablen Schwellenwert. Dieser Schwellenwert wird während der Prozessausführung kontinuierlich angepasst.

- Die <xref:System.GC.Collect%2A?displayProperty=nameWithType> -Methode wird aufgerufen. In fast allen Fällen müssen Sie diese Methode nicht aufrufen, da der Garbage Collector kontinuierlich ausgeführt wird. Diese Methode wird hauptsächlich für eindeutige Situationen und für Tests verwendet.

## <a name="the-managed-heap"></a>Der verwaltete Heap

Nachdem der Garbage Collector von der CLR initialisiert wurde, belegt er ein Arbeitsspeichersegment für die Speicherung und Verwaltung von Objekten. Dieser Speicher wird als verwalteter Heap bezeichnet, im Gegensatz zu einem systemeigenen Heap im Betriebssystem.

Es gibt einen verwalteten Heap für jeden verwalteten Prozess. Alle Threads im Prozess ordnen Speicher zu, für Objekte auf dem gleichen Heap.

Zum Reservieren von Speicher ruft der Garbage Collector die [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc)-Windows-Funktion auf und reserviert jeweils ein Segment des Speichers für verwaltete Anwendungen. Zudem reserviert der Garbage Collector nach Bedarf weitere Segmente und gibt Segmente wieder für das Betriebssystem frei (nachdem alle Objekte aus diesen entfernt wurden), indem er die [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree)-Windows-Funktion aufruft.

> [!IMPORTANT]
> Die Größe der Segmente, die vom Garbage Collector zugeordnet werden, ist implementierungsspezifisch und kann jederzeit, auch in regelmäßigen Updates, geändert werden. Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen noch darf in ihr versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren.

Je weniger Objekte dem Heap zugeordnet sind, desto geringer ist der Arbeitsaufwand für den Garbage Collector. Wenn Sie Objekte zuordnen, verwenden Sie keine aufgerundeten Werte, die größer sind als die tatsächlichen Anforderungen. Belegen Sie z. B. kein Array von 32 Byte, wenn Sie nur 15 Byte benötigen.

Wenn eine Garbage Collection ausgelöst wird, gibt der Garbage Collector den Speicher frei, der von inaktiven Objekten belegt wird. Bei der Freigabe von Speicher werden aktive Objekte komprimiert, damit sie zusammen verschoben werden, und der inaktive Speicherplatz wird entfernt, sodass der Heap kleiner wird. Dadurch wird sichergestellt, dass Objekte, die gemeinsam zugeordnet wurden, auf dem verwalteten Heap zusammenbleiben, um ihre Lokalität beizubehalten.

Die Intrusivität (Häufigkeit und Dauer) von Garbage Collections wird bestimmt durch den Umfang der Speicherbelegungen und der Größe des beibehaltenen Speichers auf dem verwalteten Heap.

Der Heap kann als Ansammlung von zwei Heaps betrachtet werden: der [große Objektheap](large-object-heap.md) und der kleine Objektheap.

Der [große Objektheap](large-object-heap.md) enthält sehr große Objekte, die mindestens 85.000 Bytes groß sind. Die Objekte auf dem großen Objektheap sind normalerweise Arrays. Ein Instanzobjekt ist meistens nicht sehr groß.

> [!TIP]
> Sie können [den Schwellenwert](../../core/run-time-config/garbage-collector.md#large-object-heap-threshold) für die Objekte im großen Objektheap festlegen.

## <a name="generations"></a>Generationen

Der Heap ist in Generationen organisiert, damit er langlebige und kurzlebige Objekte behandeln kann. Die Garbage Collection tritt hauptsächlich in Verbindung mit der Freigabe kurzlebiger Objekte auf, die in der Regel nur einen kleinen Teil des Heaps belegen. Auf dem Heap gibt es drei Generationen von Objekten:

- **Generation 0**. Dies ist die jüngste Generation, die kurzlebige Objekte enthält. Ein Beispiel für ein kurzlebiges Objekt ist eine temporäre Variable. Die Garbage Collection tritt am häufigsten in dieser Generation auf.

  Neu zugeordnete Objekte bilden eine neue Generation von Objekten und sind implizit Sammlungen der Generation 0. Wenn es sich jedoch um große Objekte handelt, werden sie im großen Objektheap in einer Sammlung der Generation 2 verwaltet.

  Die meisten Objekte werden bei einer Garbage Collection in Generation 0 freigegeben und bleiben nicht bis zur nächsten Generation aktiv.

- **Generation 1**. Diese Generation enthält kurzlebige Objekte und dient als Puffer zwischen kurzlebigen Objekten und langlebigen Objekten.

- **Generation 2**. Diese Generation enthält langlebige Objekte. Ein Beispiel für ein langlebiges Objekt ist ein Objekt in einer Serveranwendung, das statische Daten enthält, die für die Dauer des Prozesses aktiv sind.

Garbage Collections finden für bestimmte Generationen statt, wenn die Bedingungen dies erfordern. Das Durchführen einer Sammlung für eine Generation bedeutet, dass Objekte in dieser Generation und in allen jüngeren Generationen gesammelt werden. Eine Garbage Collection für Generation 2 wird auch als vollständige Garbage Collection bezeichnet, da hierbei alle Objekte in allen Generationen (das heißt, alle Objekte im verwalteten Heap) freigegeben werden.

### <a name="survival-and-promotions"></a>Beibehaltene Objekte und Höherstufungen

Objekte, die bei einer Garbage Collection nicht freigegeben werden, werden als beibehaltene Objekte bezeichnet und auf die nächste Generation höher gestuft. Objekte, die nach einer Garbage Collection in Generation 0 noch vorhanden sind, werden auf Generation 1 höher gestuft; Objekte, die nach einer Garbage Collection in Generation 1 noch vorhanden sind, werden auf Generation 2 höher gestuft. Objekte, die nach einer Garbage Collection Generation 2 noch vorhanden sind, bleiben in Generation 2.

Wenn der Garbage Collector erkennt, dass die Rate der beibehaltenen Objekte in einer Generation hoch ist, erhöht er den Schwellenwert der Zuteilungen für diese Generation. Somit wird bei der nächsten Garbage Collection eine beträchtliche Menge an Speicherplatz freigegeben. Die CLR wägt ständig zwei Prioritäten gegeneinander ab: Zum einen soll das Workingset einer Anwendung durch die Verzögerung der Garbage Collection nicht zu groß werden, und zum anderen soll die Garbage Collection nicht zu häufig ausgeführt werden.

### <a name="ephemeral-generations-and-segments"></a>Kurzlebige Generationen und Segmente

Da Objekte in der Generation 0 und 1 kurzlebig sind, werden diese Generationen als kurzlebige Generationen bezeichnet.

Kurzlebige Generationen müssen das Speichersegment belegen, das als kurzlebiges Segment bezeichnet wird. Jedes neue vom Garbage Collector abgerufene Segment wird das neue kurzlebige Segment und enthält die Objekte, die nach einer Garbage Collection in Generation 0 noch bestehen. Das alte kurzlebige Segment wird das neue Segment der Generation 2.

Die Größe des kurzlebigen Segments variiert abhängig davon, ob ein System ein 32-Bit- oder ein 64-Bit-System ist, und welchen Typ der Garbage Collector hat, der ausgeführt wird. Die Standardwerte sind in der folgenden Tabelle aufgeführt.

||32-Bit|64 Bit|
|-|-------------|-------------|
|Arbeitsstation-GC|16 MB|256 MB|
|Server-GC|64 MB|4 GB|
|Server-GC mit > 4 logischen CPUs|32 MB|2 GB|
|Server-GC mit > 8 logischen CPUs|16 MB|1 GB|

Das kurzlebige Segment kann Objekte der Generation 2 einschließen. Objekte der Generation 2 können mehrere Segmente verwenden (so viele, wie der Prozess erfordert und für den Speicher vorgesehen sind).

Die Menge an Speicher, der bei einer kurzlebigen Garbage Collection freigegeben wird, ist auf die Größe des kurzlebigen Segments beschränkt. Der Umfang des freigegebenen Speichers ist proportional zum Speicherplatz, der von den inaktiven Objekten belegt wurde.

## <a name="what-happens-during-a-garbage-collection"></a>Was geschieht während einer Garbage Collection

Eine Garbage Collection umfasst die folgenden Phasen:

- Eine Markierungsphase, die eine Liste aller aktiven Objekte ermittelt und erstellt.

- Eine Neuzuordnungsphase, in der die Verweise auf die zu komprimierenden Objekte aktualisiert werden.

- Eine Komprimierungsphase, in der der von den inaktiven Objekten belegte Speicherplatz freigegeben und die noch bestehenden Objekte komprimiert werden. In der Komprimierungsphase werden die Objekte, die nach einer Garbage Collection noch vorhanden sind, zum älteren Ende des Segments verschoben.

  Da Auflistungen der Generation 2 mehrere Segmente belegen können, können Objekte, die auf Generation 2 höher gestuft werden, in ein älteres Segment verschoben werden. Objekte, die sowohl Generation 1 als auch Generation 2 überlebt haben, können in ein anderes Segment verschoben werden, da sie auf Generation 2 höher gestuft werden.

  Normalerweise wird der große Objektheap (LOH) nicht komprimiert, da das Kopieren großer Objekte Leistungseinbußen zur Folge hat. In .NET Core und ab .NET Framework 4.5.1 können Sie jedoch die Eigenschaft <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> verwenden, um bei Bedarf den großen Objektheap zu komprimieren. Außerdem wird der LOH automatisch komprimiert, wenn eine feste Grenze festgelegt wird, indem Folgendes angegeben wird:

  - ein Arbeitsspeicherlimit für einen Container oder
  - die [GCHeapHardLimit](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitcomplus_gcheaphardlimit)- oder [GCHeapHardLimitPercent](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent)-Laufzeitkonfigurationsoptionen

Der Garbage Collector bestimmt anhand folgender Informationen, ob Objekte aktiv sind:

- **Stapelstämme**. Vom Just-In-Time (JIT)-Compiler bereitgestellte Stapelvariablen und Stackwalker. Durch JIT-Optimierungen können Bereiche des Codes, in denen Stapelvariablen dem Garbage Collector gemeldet werden, verlängert oder verkürzt werden.

- **Garbage Collection-Handles**. Diese Handles zeigen auf verwaltete Objekte und können vom Benutzercode oder der Common Language Runtime zugeordnet werden.

- **Statische Daten**. Statische Objekte in Anwendungsdomänen, die auf andere Objekte verweisen können. Jede Anwendungsdomäne verfolgt die eigenen statischen Objekte.

Vor dem Start einer Garbage Collection werden alle verwalteten Threads bis auf den Thread, der die Garbage Collection ausgelöst hat, angehalten.

Die folgende Abbildung zeigt einen Thread, der eine Garbage Collection auslöst und eine Unterbrechung der Ausführung anderer Threads verursacht.

![Garbage Collection, die durch einen Thread ausgelöst wird](./media/gc-triggered.png)

## <a name="manipulate-unmanaged-resources"></a>Bearbeiten von nicht verwalteten Ressourcen

Wenn die verwalteten Objekte mit ihren nativen Dateihandles auf nicht verwaltete Objekte verweisen, müssen Sie die nicht verwalteten Objekte explizit freigeben, da der Garbage Collector den Speicher nur für den verwalteten Heap verfolgt.

Benutzer des verwalteten Objekts geben möglicherweise nicht die nativen Ressourcen frei, die vom Objekt verwendet werden. Um die Bereinigung auszuführen, können Sie das verwaltete Objekt abschließen. Der Abschluss umfasst Bereinigungsaktionen, die Sie ausführen, wenn das Objekt nicht mehr verwendet wird. Wenn das verwaltete Objekt nicht mehr aktiv ist, führt es Bereinigungsaktionen aus, die in der Finalizer-Methode angegeben sind.

Wenn festgestellt wird, dass ein abzuschließendes Objekt inaktiv ist, wird der Finalizer des Objekts in eine Warteschlange eingereiht, damit die dazugehörigen Bereinigungsaktionen ausgeführt werden. Das Objekt selbst wird jedoch auf die nächste Generation höher gestuft. Daher müssen Sie bis zur nächsten Garbage Collection warten, die für diese Generation stattfindet (dies ist nicht notwendigerweise die nächste Garbage Collection), um zu bestimmen, ob das Objekt freigegeben wurde.

Weitere Informationen zur Finalisierung finden Sie unter <xref:System.Object.Finalize?displayProperty=nameWithType>.

## <a name="workstation-and-server-garbage-collection"></a>Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server

Der Garbage Collector optimiert sich selbst und kann in einer Vielzahl von Szenarien funktionieren. Sie können die [Einstellung einer Konfigurationsdatei](../../core/run-time-config/garbage-collector.md#flavors-of-garbage-collection) verwenden, um den Typ der Garbage Collection basierend auf den Merkmalen der Arbeitsauslastung festzulegen. Die CLR stellt mehrere Arten der Garbage Collection bereit:

- Die Garbage Collection (GC) für die Arbeitsstation ist für Client-Apps konzipiert. Dies ist die GC-Standardkonfiguration für eigenständige Apps. Für gehostete Apps, z. B. die von ASP.NET gehosteten Apps, bestimmt der Host die GC-Standardkonfiguration.

  Die Garbage Collection für die Arbeitsstation kann gleichzeitig oder nicht gleichzeitig erfolgen. Die gleichzeitige Garbage Collection ermöglicht, dass verwaltete Threads während einer Garbage Collection Vorgänge fortgesetzt werden können. Ab .NET Framework 4 wird die [gleichzeitige Garbage Collection](#background-workstation-garbage-collection) durch die [Garbage Collection im Hintergrund](#concurrent-garbage-collection) ersetzt.

- Garbage Collection für Server, die für Serveranwendungen vorgesehen ist, die einen hohen Durchsatz und eine hohe Skalierbarkeit erfordern.

  - In .NET Core kann die Garbage Collection auf dem Server nicht-gleichzeitig oder im Hintergrund ausgeführt werden.

  - Ab .NET Framework 4.5 kann die Garbage Collection auf dem Server nicht-gleichzeitig oder im Hintergrund ausgeführt werden (die Garbage Collection im Hintergrund ersetzt die gleichzeitige Garbage Collection). In .NET Framework 4 und früheren Versionen erfolgt die Garbage Collection auf dem Server gleichzeitig.

Die folgende Abbildung zeigt die dedizierten Threads, die die Garbage Collection auf einem Server ausführen:

![Threads für Garbage Collection auf dem Server](./media/gc-server.png)

### <a name="compare-workstation-and-server-garbage-collection"></a>Vergleich der Garbage Collection für die Arbeitsstation und der Garbage Collection auf dem Server

Im Folgenden finden Sie Überlegungen zu Threading und Leistung der Garbage Collection auf Arbeitsstationen:

- Die Garbage Collection erfolgt auf dem Benutzerthread, der die Garbage Collection ausgelöst hat, und die Priorität bleibt unverändert. Da Benutzerthreads in der Regel mit normaler Priorität ausgeführt werden, muss der Garbage Collector (der auf einem Thread mit normaler Priorität ausgeführt wird) mit anderen Threads um CPU-Zeit konkurrieren. (Threads, die nativen Code ausführen, werden bei der Garbage Collection für die Arbeitsstation bzw. auf dem Server nicht angehalten.)

- Die Garbage Collection für die Arbeitsstation wird immer auf einem Computer verwendet, der nur einen Prozessor besitzt, unabhängig von der [Konfigurationseinstellung](../../core/run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).

Im Folgenden finden Sie Überlegungen zu Threading und Leistung der Garbage Collection auf Servern:

- Die Garbage Collection erfolgt auf mehreren dedizierten Threads, die mit der Prioritätsebene `THREAD_PRIORITY_HIGHEST` ausgeführt werden.

- Für jede CPU werden ein Heap und ein dedizierter Thread zum Ausführen der Garbage Collection bereitgestellt, und die Auflistung für die Heaps findet zur gleichen Zeit statt. Jeder Heap enthält einen kleinen Objektheap und einen großen Objektheap, und auf alle Heaps kann über den Benutzercode zugegriffen werden. Objekte auf verschiedenen Heaps können aufeinander verweisen.

- Da mehrere Garbage Collection-Threads zusammenarbeiten, ist die Garbage Collection auf dem Server bei gleicher Heapgröße schneller als die Garbage Collection für die Arbeitsstation.

- Bei der Garbage Collection auf dem Server sind die Segmente häufig größer. Dies ist jedoch nur eine allgemeine Angabe: Die Segmentgröße ist implementierungsspezifisch und unterliegt möglicherweise Änderungen. Wenn Sie eine Anwendung optimieren, sollten Sie keine Annahmen über die Größe der Segmente machen, die vom Garbage Collector zugeordnet werden.

- Die Garbage Collection auf dem Server kann ressourcenintensiv sein. Nehmen Sie beispielsweise an, dass auf einem Computer mit vier Prozessoren zwölf Prozesse vorhanden sind, in denen die Garbage Collection auf dem Server ausgeführt wird. Wenn alle Prozesse die Garbage Collection gleichzeitig durchführen, würden sie sich gegenseitig behindern, da auf demselben Prozessor zwölf Threads geplant würden. Wenn die Prozesse aktiv sind, ist es nicht empfehlenswert, dass sie alle die Garbage Collection auf dem Server verwenden.

Wenn Sie Hunderte von Instanzen einer Anwendung ausführen, sollten Sie erwägen, eine Garbage Collection für die Arbeitsstation mit deaktivierter gleichzeitiger Garbage Collection zu verwenden. Dies führt zu weniger Kontextwechseln, wodurch die Leistung verbessert werden kann.

## <a name="background-workstation-garbage-collection"></a>Garbage Collection auf Arbeitsstationen im Hintergrund

Bei der Garbage Collection im Hintergrund auf Arbeitsstationen werden kurzlebige Generationen (0 und 1) bei Bedarf bereinigt, während die Garbage Collection von Generation 2 ausgeführt wird. Die Garbage Collection auf Arbeitsstationen im Hintergrund wird auf einem dedizierten Thread ausgeführt und betrifft nur die Garbage Collections der Generation 2.

Die Garbage Collection im Hintergrund ist standardmäßig aktiviert und kann mit der Konfigurationseinstellung [gcConcurrent](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) in .NET Framework-Apps oder der Einstellung [System.GC.Concurrent](../../core/run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent) in .NET Core-Apps aktiviert oder deaktiviert werden.

> [!NOTE]
> Ab .NET Framework 4 ersetzt die Garbage Collection im Hintergrund die [gleichzeitige Garbage Collection](#concurrent-garbage-collection). In .NET Framework 4 wird sie nur für die Garbage Collection für Arbeitsstationen unterstützt. Ab .NET Framework 4.5 ist die Garbage Collection im Hintergrund für Arbeitsstationen und Server verfügbar.

Eine Garbage Collection für kurzlebige Generationen, die während der Garbage Collection im Hintergrund stattfindet, wird als Garbage Collection im Vordergrund bezeichnet. Wenn Garbage Collections im Vordergrund stattfinden, werden alle verwalteten Threads angehalten.

Wenn eine Garbage Collection im Hintergrund ausgeführt wird und Sie genügend Objekte in Generation 0 zugeordnet haben, führt die CLR eine Garbage Collection der Generation 0 oder der Generation 1 im Vordergrund aus. Der dedizierte Thread der Garbage Collection im Hintergrund prüft häufig, ob eine Anforderung für die Garbage Collection im Vordergrund besteht. Trifft dies zu, wird die Garbage Collection im Hintergrund angehalten, damit die Garbage Collection im Vordergrund stattfinden kann. Nachdem die Garbage Collection im Vordergrund abgeschlossen wurde, werden der dedizierte Thread der Garbage Collection im Hintergrund und die Benutzerthreads fortgesetzt.

Die Garbage Collection im Hintergrund beseitigt die von der gleichzeitigen Garbage Collection auferlegten Speicherbelegungseinschränkungen, da kurzlebige Garbage Collections während der Garbage Collection im Hintergrund stattfinden können. Mit der Garbage Collection im Hintergrund können inaktive Objekte in kurzlebigen Generationen entfernt werden. Ferner kann der Heap bei Bedarf während einer Garbage Collection der Generation 1 erweitert werden.

Die folgende Abbildung zeigt eine Garbage Collection im Hintergrund für einen separaten dedizierten Thread auf einer Arbeitsstation:

![Garbage Collection auf Arbeitsstationen im Hintergrund](./media/fundamentals/background-workstation-garbage-collection.png)

### <a name="background-server-garbage-collection"></a>Garbage Collection auf dem Server im Hintergrund

Ab .NET Framework 4.5 ist die Garbage Collection im Hintergrund der Standardmodus für die Garbage Collection auf dem Server.

Die Garbage Collection im Hintergrund auf dem Server ähnelt der im vorherigen Abschnitt beschriebenen Garbage Collection im Hintergrund auf einer Arbeitsstation, es gibt jedoch einige Unterschiede:

- Die Garbage Collection im Hintergrund auf der Arbeitsstation verwendet einen dedizierten Thread für die Garbage Collection im Hintergrund, während die Garbage Collection im Hintergrund auf dem Server mehrere Threads verwendet. In der Regel wird ein dedizierter Thread für jeden logischen Prozessor verwendet.

- Anders als der Garbage Collection-Thread im Hintergrund auf einer Arbeitsstation tritt bei diesen Threads kein Timeout auf.

Die folgende Abbildung zeigt eine Garbage Collection im Hintergrund für einen separaten dedizierten Thread auf einem Server:

![Garbage Collection auf dem Server im Hintergrund](./media/fundamentals/background-server-garbage-collection.png)

## <a name="concurrent-garbage-collection"></a>Concurrent garbage collection

> [!TIP]
> Dieser Abschnitt gilt für:
>
> - .NET Framework 3.5 und früher für die Garbage Collection für Arbeitsstationen
> - .NET Framework 4 und früher für die Garbage Collection auf dem Server
>
> Die gleichzeitige Garbage Collection wird in späteren Versionen durch die [Garbage Collection im Hintergrund](#background-workstation-garbage-collection) ersetzt.

Bei der Garbage Collection für Arbeitsstationen oder Server können Sie die [gleichzeitige Garbage Collection aktivieren](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md). Diese ermöglicht die gleichzeitige Ausführung von Threads mit einem dedizierten Thread, der die Garbage Collection nahezu die ganze Zeit ausführt. Diese Option wirkt sich nur auf Garbage Collections in Generation 2 aus; in Generation 0 und 1 finden keine gleichzeitigen Garbage Collections statt, da sie sehr schnell beendet werden.

Dank der gleichzeitigen Garbage Collection ist die Reaktionsfähigkeit interaktiver Anwendungen besser, da die für die Garbage Collection notwendigen Pausen minimiert werden. Verwaltete Threads können weiterhin die meiste Zeit ausgeführt werden, während der Thread der gleichzeitigen Garbage Collection ausgeführt wird. Dies verkürzt die Pausen während einer Garbage Collection.

Die gleichzeitige Garbage Collection wird auf einem dedizierten Thread ausgeführt. Standardmäßig führt die CLR die Garbage Collection für die Arbeitsstation mit aktivierter gleichzeitiger Garbage Collection aus. Dies gilt für Einzelprozessor- und für Mehrprozessorcomputer.

Die folgende Abbildung zeigt eine parallele Garbage Collection für einen separaten dedizierten Thread.

![Threads für parallele Garbage Collection](./media/gc-concurrent.png)

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsoptionen für die Garbage Collection](../../core/run-time-config/garbage-collector.md)
- [Garbage Collection](index.md)
