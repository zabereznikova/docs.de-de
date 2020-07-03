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
ms.openlocfilehash: 438188b6d694bdeab772c43ef92e5621c68facff
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990215"
---
# <a name="fundamentals-of-garbage-collection"></a>Grundlagen der Garbage Collection

In der Common Language Runtime (CLR) dient der Garbage Collector (GC) als automatischer Speicher-Manager. Der Garbage Collector verwaltet die Belegung und Freigabe von Arbeitsspeicher für eine Anwendung. Das bedeutet, dass beim Entwickeln mit verwaltetem Code kein Code für Aufgaben hinsichtlich der Speicherverwaltung geschrieben werden muss. Mithilfe der automatischen Speicherverwaltung können häufig auftretende Probleme beseitigt werden, z. B. wenn ein Objekt versehentlich nicht freigegeben wurde und dadurch Arbeitsspeicherverluste entstehen oder wenn auf den Speicher für ein Objekt zugegriffen wird, das bereits freigegeben wurde.

In diesem Artikel werden die wichtigsten Konzepte der Garbage Collection beschrieben.

## <a name="benefits"></a>Vorteile

Der Garbage Collector bietet die folgenden Vorteile:

- Entwickler müssen nicht mehr manuell Arbeitsspeicher freigeben.

- Ordnet dem verwalteten Heap effizient Objekte zu.

- Gibt Objekte frei, die nicht mehr verwendet werden, löscht den Speicher und hält Speicher für zukünftige Belegungen bereit. Verwaltete Objekte beginnen automatisch mit einem bereinigten Inhalt, damit ihre Konstruktoren nicht jedes Datenfeld initialisieren müssen.

- Bietet Speichersicherheit, indem sichergestellt wird, dass ein Objekt den Inhalt eines anderen Objekts nicht verwenden kann.

## <a name="fundamentals-of-memory"></a>Grundlagen des Arbeitsspeichers

Die folgende Liste liefert eine Zusammenfassung wichtiger Arbeitsspeicherkonzepte der CLR.

- Jeder Prozess verfügt über einen eigenen separaten virtuellen Adressraum. Alle Prozesse auf demselben Computer verwenden den gleichen physischen Speicher und die gleiche Auslagerungsdatei, sofern vorhanden.

- In der Standardeinstellung verfügt jeder Prozess auf 32-Bit-Computern über einen virtuellen Adressraum von 2 GB im Benutzermodus.

- Als Anwendungsentwickler arbeiten Sie immer mit einem virtuellem Adressraum und manipulieren niemals direkt den physischen Speicher. Der Garbage Collector belegt und gibt virtuellen Arbeitsspeicher auf dem verwalteten Heap frei.

  Wenn Sie nativen Code schreiben, verwenden Sie die Windows-Funktionen für das Arbeiten mit dem virtuellen Adressraum. Diese Funktionen belegen und geben für Sie virtuellen Arbeitsspeicher auf systemeigenen Heaps frei.

- Virtueller Arbeitsspeicher kann sich in einem von drei Zuständen befinden:

  | Zustand | Beschreibung |
  |---------|---------|
  | Kostenlos | Es sind keine Verweise auf den Speicherblock vorhanden, und der Speicherblock ist für eine Speicherbelegung verfügbar. |
  | Reserviert | Der Speicherblock ist für die Verwendung verfügbar und kann nicht durch andere Anforderungen belegt werden. Sie können jedoch keine Daten in diesem Speicherblock speichern, bis eine Zusicherung erfolgt ist. |
  | Committet | Der Speicherblock ist einem physischen Speicher zugewiesen. |

- Im virtuellen Adressraum können Fragmentierungen auftreten. Das bedeutet, dass freie Blöcke (Lücken) im Adressraum vorhanden sind. Wenn eine virtuelle Speicherbelegung angefordert wird, muss der Manager für virtuellen Arbeitsspeicher einen einzelnen freien Block finden, der groß genug ist, um die Belegungsanforderung zu erfüllen. Selbst wenn 2 GB freier Speicherplatz verfügbar sind, schlägt eine Speicherbelegung, die 2 GB angefordert hat, fehl, wenn der freie Speicherplatz nicht in einem einzelnen Adressblock verfügbar ist.

- Es kann vorkommen, dass nicht mehr genügend Arbeitsspeicher zur Verfügung steht, weil der für Belegungen verfügbare virtuelle Adressraum oder der für Zusicherungen verfügbare physische Speicher nicht mehr ausreicht.

  Die Auslagerungsdatei wird auch dann verwendet, wenn der tatsächliche physische Speicherbedarf insgesamt eher niedrig ist. Wenn das erste Mal eine hohe physische Speicherauslastung auftritt, muss das Betriebssystem im physischen Speicher freien Platz für die Datenspeicherung schaffen. Zu diesem Zweck werden einige Daten aus dem physischen Speicher in die Auslagerungsdatei verschoben. Für diese Daten erfolgt solange keine neue Speicherzuordnung, bis sie tatsächlich benötigt werden. Daher können Situationen entstehen, in denen auch bei einer geringen physischen Speicherauslastung Daten in der Auslagerungsdatei abgelegt sind.
  
### <a name="memory-allocation"></a>Arbeitsspeicherbelegung

Wenn Sie einen neuen Prozess initialisieren, wird diesem durch die Common Language Runtime ein zusammenhängender Adressraum reserviert. Dieser reservierte Adressraum wird als verwalteter Heap bezeichnet. Im verwalteten Heap steht ein Zeiger zur Verfügung, der auf die Adresse des nächsten im Heap zu speichernden Objekts zeigt. Anfangs ist dieser Zeiger auf die Basisadresse des verwalteten Heaps eingestellt. Alle Referenztypen werden im verwalteten Heap zugewiesen. Wurde von einer Anwendung der erste Referenztyp erstellt, wird für diesen Typ an der Basisadresse des verwalteten Heaps Speicherplatz belegt. Wenn das nächste Objekt von der Anwendung erstellt wird, belegt der Garbage Collector Speicherplatz im Adressraum direkt hinter dem ersten Objekt. Solange ein Adressbereich verfügbar ist, fährt der Garbage Collector auf diese Weise mit der Belegung von Arbeitsspeicher für neue Objekte fort.

Das Belegen von Speicher im verwalteten Heap beansprucht weniger Zeit als die nicht verwaltete Speicherbelegung. Da durch die Common Language Runtime Speicher für ein Objekt durch Hinzufügen eines Werts zu einem Zeiger belegt wird, ist diese Methode fast so schnell wie das Reservieren von Speicher im Stapel. Außerdem werden neue Objekte, für die Speicher reserviert wird, ständig nacheinander im verwalteten Heap gespeichert. Dadurch kann eine Anwendung schnell auf diese Objekte zugreifen.

### <a name="memory-release"></a>Speicherfreigabe

Durch die Optimierungs-Engine des Garbage Collectors wird der beste Zeitpunkt für das Ausführen einer Garbage Collection bestimmt, die auf den erfolgten Speicherbelegungen basiert. Beim Ausführen einer Garbage Collection wird Speicher freigegeben, den von der Anwendung nicht mehr benötigte Objekte beanspruchen. Durch Überprüfen der *Stammelemente* der Anwendung wird ermittelt, welche Objekte nicht mehr verwendet werden. Die Stammelemente einer Anwendung beinhalten statische Felder, lokale Variablen und Parameter im Stapel des Threads sowie CPU-Register. Jedes Stammelement bezieht sich entweder auf ein Objekt im verwalteten Heap oder ist auf NULL festgelegt. Der Garbage Collector hat Zugriff auf eine Liste der aktiven Stammelemente, die vom JIT-Compiler (Just-In-Time) und der Common Language Runtime verwaltet wird. Mithilfe dieser Liste erstellt der Garbage Collector ein Diagramm mit allen Objekten, die von den Stammelementen aus erreichbar sind.

Objekte, die nicht in diesem Diagramm aufgeführt werden, können von den Stammelementen aus nicht erreicht werden. Diese nicht erreichbaren Objekte werden vom Garbage Collector als Abfall betrachtet, und der von diesen Objekten belegte Speicherplatz wird wieder freigegeben. Während einer Garbage Collection wird der verwaltete Heap nach den Blöcken des Adressraums durchsucht, in denen sich nicht erreichbare Objekte befinden. Beim Auffinden dieser Objekte werden die erreichbaren Objekte mithilfe einer Speicherkopierfunktion im Speicher komprimiert, und die von den nicht erreichbaren Objekten belegten Blöcke des Adressraums werden freigegeben. Nach dem Komprimieren des Speichers für die erreichbaren Objekte werden vom Garbage Collector die erforderlichen Korrekturen am Zeiger vorgenommen, sodass die Stammelemente der Anwendung auf die neuen Speicherorte der Objekte verweisen. Außerdem wird der Zeiger des verwalteten Heaps auf die Position hinter dem letzten erreichbaren Objekt gesetzt.

Der Speicher wird nur dann komprimiert, wenn in der Garbage Collection eine signifikante Anzahl nicht erreichbarer Objekte gefunden wird. Wenn nach einer Garbage Collection alle Objekte in einem verwalteten Heap verbleiben, bedarf es auch keiner Speicherkomprimierung.

Um die Leistung zu verbessern, wird für große Objekte durch die Common Language Runtime Speicherplatz in einem separaten Heap belegt. Der Speicherplatz für große Objekte wird durch den Garbage Collector automatisch freigegeben. Dieser Speicher wird jedoch nicht komprimiert, um das Verschieben großer Objekte im Speicher zu vermeiden.

## <a name="conditions-for-a-garbage-collection"></a>Bedingungen für eine Garbage Collection

Eine Garbage Collection wird durchgeführt, wenn eine der folgenden Bedingungen zutrifft:

- Das System verfügt über einen kleinen physikalischen Speicher. Dies wird entweder durch die Meldung des Betriebssystems über zu wenig Arbeitsspeicher oder durch die Meldung des Hosts über zu wenig Arbeitsspeicher erkannt.

- Der Speicher, der von den zugeordneten Objekten auf dem verwalteten Heap belegt ist, übersteigt einen akzeptablen Schwellenwert. Dieser Schwellenwert wird während der Prozessausführung kontinuierlich angepasst.

- Die <xref:System.GC.Collect%2A?displayProperty=nameWithType> -Methode wird aufgerufen. In fast allen Fällen müssen Sie diese Methode nicht aufrufen, da der Garbage Collector kontinuierlich ausgeführt wird. Diese Methode wird hauptsächlich für eindeutige Situationen und für Tests verwendet.

## <a name="the-managed-heap"></a>Der verwaltete Heap

Nachdem der Garbage Collector von der CLR initialisiert wurde, belegt er ein Arbeitsspeichersegment für die Speicherung und Verwaltung von Objekten. Dieser Speicher wird als verwalteter Heap bezeichnet, im Gegensatz zu einem systemeigenen Heap im Betriebssystem.

Es gibt einen verwalteten Heap für jeden verwalteten Prozess. Alle Threads im Prozess ordnen Speicher zu, für Objekte auf dem gleichen Heap.

Zum Reservieren von Speicher ruft der Garbage Collector die [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc)-Windows-Funktion auf und reserviert jeweils ein Segment des Speichers für verwaltete Anwendungen. Zudem reserviert der Garbage Collector nach Bedarf weitere Segmente und gibt Segmente wieder für das Betriebssystem frei (nachdem alle Objekte aus diesen entfernt wurden), indem er die [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree)-Windows-Funktion aufruft.

> [!IMPORTANT]
> Die Größe der Segmente, die vom Garbage Collector zugeordnet werden, ist implementierungsspezifisch und kann jederzeit, auch in regelmäßigen Updates, geändert werden. Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen noch darf in ihr versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren.

Je weniger Objekte dem Heap zugeordnet sind, desto geringer ist der Arbeitsaufwand für den Garbage Collector. Verwenden Sie beim Zuordnen von Objekten keine aufgerundeten Werte, die größer sind als die tatsächlichen Anforderungen. Belegen Sie z. B. kein Array von 32 Byte, wenn Sie nur 15 Byte benötigen.

Wenn eine Garbage Collection ausgelöst wird, gibt der Garbage Collector den Speicher frei, der von inaktiven Objekten belegt wird. Bei der Freigabe von Speicher werden aktive Objekte komprimiert, damit sie zusammen verschoben werden, und der inaktive Speicherplatz wird entfernt, sodass der Heap kleiner wird. Dadurch wird sichergestellt, dass gemeinsam zugeordnete Objekte auf dem verwalteten Heap zusammenbleiben, um ihren Speicherort beizubehalten.

Die Intrusivität (Häufigkeit und Dauer) von Garbage Collections wird bestimmt durch den Umfang der Speicherbelegungen und der Größe des beibehaltenen Speichers auf dem verwalteten Heap.

Der Heap kann als Ansammlung von zwei Heaps betrachtet werden: der [große Objektheap](large-object-heap.md) und der kleine Objektheap. Der große Objektheap enthält Objekte, die mindestens 85.000 Bytes oder mehr umfassen und bei denen es sich in der Regel um Arrays handelt. Ein Instanzobjekt ist meistens nicht sehr groß.

> [!TIP]
> Sie können [den Schwellenwert](../../core/run-time-config/garbage-collector.md#large-object-heap-threshold) für die Objekte im großen Objektheap festlegen.

## <a name="generations"></a>Generationen

Der GC-Algorithmus basiert auf mehreren Überlegungen:

- Die Garbage Collection kann schneller ausgeführt werden, wenn der Speicher nur in einem Teil des verwalteten Heaps und nicht im gesamten Heap komprimiert wird.
- Neuere Objekte haben eine kürzere, ältere Objekte hingegen eine längere Lebensdauer.
- Neuere Objekte tendieren dazu, miteinander in Beziehung zu stehen, und die Anwendung greift etwa zur gleichen Zeit auf sie zu.

Die Garbage Collection wird hauptsächlich in Verbindung mit der Freigabe kurzlebiger Objekte ausgeführt. Der verwaltete Heap wird zur Leistungsoptimierung des Garbage Collectors in die drei Generationen 0, 1 und 2 unterteilt, sodass er langlebige und kurzlebige Objekte separat verarbeiten kann. Der Garbage Collector speichert neue Objekte in Generation 0. Objekte, die früh in der Lebensdauer der Anwendung erstellt wurden und nach den Garbage Collections noch vorhanden sind, werden höher gestuft und werden in Generationen 1 und 2 gespeichert. Da es weniger Zeit beansprucht, statt des gesamten verwalteten Heaps nur einen Teil davon zu komprimieren, ist es bei diesem Konzept auch möglich, bei einer Garbage Collection lediglich Speicher einer bestimmten Generationsstufe und nicht den des gesamten verwalteten Heaps freizugeben.

- **Generation 0**. Dies ist die jüngste Generation, die kurzlebige Objekte enthält. Ein Beispiel für ein kurzlebiges Objekt ist eine temporäre Variable. Die Garbage Collection tritt am häufigsten in dieser Generation auf.

  Neu zugeordnete Objekte bilden eine neue Generation von Objekten und sind implizit Sammlungen der Generation 0. Wenn es sich jedoch um große Objekte handelt, werden sie im großen Objektheap verwaltet, der manchmal auch als *Generation 3* bezeichnet wird. Generation 3 ist eine physische Generation, die logisch als Teil der Generation 2 erfasst wird.

  Die meisten Objekte werden bei einer Garbage Collection für Generation 0 freigegeben und bleiben nicht bis zur nächsten Generation aktiv.
  
  Wenn Generation 0 voll ist und eine Anwendung versucht, ein neues Objekt zu erstellen, führt der Garbage Collector eine Collection durch, um Adressraum für das neue Objekt freizugeben. Dabei werden nur die Objekte im Bereich der Generation 0 untersucht und nicht alle Objekte im verwalteten Heap. Eine Garbage Collection für Generation 0 liefert oftmals ausreichend Speicherplatz, sodass von der Anwendung weitere neue Objekte erzeugt werden können.

- **Generation 1**. Diese Generation enthält kurzlebige Objekte und dient als Puffer zwischen kurzlebigen Objekten und langlebigen Objekten.

  Nach Durchführung einer Garbage Collection für Generation 0 wird der Speicher für die erreichbaren Objekte komprimiert, die dann auf Generation 1 hochgestuft werden. Da Objekte, die nach Garbage Collections noch vorhanden sind, normalerweise längere Lebensdauern haben, ist es sinnvoll, sie auf eine höhere Generation heraufzustufen. Der Garbage Collector muss die Objekte in Generation 1 und 2 nicht jedes Mal aufs Neue untersuchen, wenn eine Collection für Generation 0 durchgeführt wird.
  
  Wenn eine Garbage Collection für Generation 0 nicht genug Speicher für die Anwendung zum Erstellen eines neuen Objekts freigibt, kann der Garbage Collector zunächst eine Collection für Generation 1 und anschließend für Generation 2 durchführen. Objekte in Generation 1, die nach den Garbage Collections noch vorhanden sind, werden auf Generation 2 hochgestuft.

- **Generation 2**. Diese Generation enthält langlebige Objekte. Ein Beispiel für ein langlebiges Objekt ist ein Objekt in einer Serveranwendung, das statische Daten enthält, die für die Dauer des Prozesses aktiv sind.

  Objekte in Generation 2, die nach einer Collection noch vorhanden sind, bleiben in Generation 2, bis sie in einer künftigen Collection als nicht erreichbar erkannt werden.
  
  Objekte im großen Objektheap (manchmal auch als *Generation 3*bezeichnet) werden auch in Generation 2 gesammelt.

Garbage Collections finden für bestimmte Generationen statt, wenn die Bedingungen dies erfordern. Das Durchführen einer Sammlung für eine Generation bedeutet, dass Objekte in dieser Generation und in allen jüngeren Generationen gesammelt werden. Eine Garbage Collection für Generation 2 wird auch als vollständige Garbage Collection bezeichnet, da hierbei alle Objekte in allen Generationen (d. h. alle Objekte im verwalteten Heap) freigegeben werden.

### <a name="survival-and-promotions"></a>Beibehaltene Objekte und Höherstufungen

Objekte, die bei einer Garbage Collection nicht freigegeben werden, werden als beibehaltene Objekte bezeichnet und auf die nächste Generation hochgestuft.

- Objekte, die nach einer Garbage Collection für Generation 0 noch vorhanden sind, werden auf Generation 1 hochgestuft.
- Objekte, die nach einer Garbage Collection für Generation 1 noch vorhanden sind, werden auf Generation 2 hochgestuft.
- Objekte, die nach einer Garbage Collection für Generation 2 noch vorhanden sind, bleiben in Generation 2.

Wenn der Garbage Collector erkennt, dass die Rate der beibehaltenen Objekte in einer Generation hoch ist, erhöht er den Schwellenwert der Zuteilungen für diese Generation. Somit wird bei der nächsten Garbage Collection eine beträchtliche Menge an Speicherplatz freigegeben. Die CLR wägt ständig zwei Prioritäten gegeneinander ab: Zum einen soll das Workingset einer Anwendung durch die Verzögerung der Garbage Collection nicht zu groß werden, und zum anderen soll die Garbage Collection nicht zu häufig ausgeführt werden.

### <a name="ephemeral-generations-and-segments"></a>Kurzlebige Generationen und Segmente

Da Objekte in Generation 0 und 1 kurzlebig sind, werden diese Generationen als *kurzlebige Generationen* bezeichnet.

Kurzlebige Generationen belegen das Speichersegment, das als kurzlebiges Segment bezeichnet wird. Jedes neue vom Garbage Collector abgerufene Segment wird das neue kurzlebige Segment und enthält die Objekte, die nach einer Garbage Collection in Generation 0 noch bestehen. Das alte kurzlebige Segment wird das neue Segment der Generation 2.

Die Größe des kurzlebigen Segments variiert abhängig davon, ob es sich um ein 32-Bit- oder ein 64-Bit-System handelt und welchen Typ der Garbage Collector aufweist, der ausgeführt wird ([Garbage Collection für Arbeitsstation oder Server](workstation-server-gc.md)). Die folgende Tabelle zeigt die Standardgrößen des kurzlebigen Segments.

|Garbage Collection für Arbeitsstationen oder Server|32-Bit|64-Bit|
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

  - Arbeitsspeicherlimit für einen Container
  - Runtimekonfigurationsoptionen [GCHeapHardLimit](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitcomplus_gcheaphardlimit) oder [GCHeapHardLimitPercent](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent)

Der Garbage Collector bestimmt anhand folgender Informationen, ob Objekte aktiv sind:

- **Stapelstämme**. Vom Just-In-Time (JIT)-Compiler bereitgestellte Stapelvariablen und Stackwalker. Durch JIT-Optimierungen können Bereiche des Codes, in denen Stapelvariablen dem Garbage Collector gemeldet werden, verlängert oder verkürzt werden.

- **Garbage Collection-Handles**. Diese Handles zeigen auf verwaltete Objekte und können vom Benutzercode oder der Common Language Runtime zugeordnet werden.

- **Statische Daten**. Statische Objekte in Anwendungsdomänen, die auf andere Objekte verweisen können. Jede Anwendungsdomäne verfolgt die eigenen statischen Objekte.

Vor dem Start einer Garbage Collection werden alle verwalteten Threads bis auf den Thread, der die Garbage Collection ausgelöst hat, angehalten.

Die folgende Abbildung zeigt einen Thread, der eine Garbage Collection auslöst und eine Unterbrechung der Ausführung anderer Threads verursacht.

![Garbage Collection, die durch einen Thread ausgelöst wird](media/gc-triggered.png)

## <a name="unmanaged-resources"></a>Nicht verwaltete Ressourcen

Mit einer Garbage Collection werden alle Aufgaben in Bezug auf die Speicherverwaltung für die meisten von einer Anwendung erstellten Objekte automatisch ausgeführt. Allerdings ist bei nicht verwalteten Ressourcen explizites Bereinigen erforderlich. Die häufigsten nicht verwalteten Ressourcen sind Objekte, die eine Betriebssystemressource umschließen, z. B. ein Dateihandle, ein Fensterhandle oder eine Netzwerkverbindung. Obwohl der Garbage Collector die Lebensdauer eines verwalteten Objekts, das eine nicht verwaltete Ressource kapselt, verfolgen kann, stehen ihm keine genauen Informationen zum Bereinigen dieser Ressource zur Verfügung.

Wenn Sie ein Objekt erstellen möchten, das eine nicht verwaltete Ressource kapselt, ist es ratsam, Code zum Bereinigen der nicht verwalteten Ressource in einer öffentlichen `Dispose`-Methode bereitzustellen. Durch Bereitstellen der `Dispose`-Methode wird Benutzern des Objekts die Möglichkeit gegeben, nicht mehr benötigten Speicherplatz explizit freizugeben, sobald das Objekt nicht mehr verwendet wird. Wenn Sie ein Objekt verwenden, das eine nicht verwaltete Ressource kapselt, sollten Sie bei Bedarf `Dispose` aufrufen.

Sorgen Sie außerdem dafür, dass die nicht verwalteten Ressourcen freigegeben werden können, falls ein Consumer Ihres Typs vergisst, `Dispose` aufzurufen. Sie können entweder ein SafeHandle zum Wrappen der nicht verwalteten Ressource verwenden oder die <xref:System.Object.Finalize?displayProperty=nameWithType>-Methode überschreiben.

Weitere Informationen zum Bereinigen nicht verwalteter Ressourcen finden Sie unter [Bereinigen von nicht verwalteten Ressourcen](unmanaged.md).

## <a name="see-also"></a>Siehe auch

- [Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server](workstation-server-gc.md)
- [Garbage Collection im Hintergrund](background-gc.md)
- [Konfigurationsoptionen für die Garbage Collection](../../core/run-time-config/garbage-collector.md)
- [Garbage Collection](index.md)
