---
title: Grundlagen der Garbage Collection
description: Grundlagen der Garbage Collection
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 9d5fce64-95a4-4609-8eee-b0ac70078cdb
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 78a2d593329f0703c71df2462cfea30b02adff85

---

# <a name="fundamentals-of-garbage-collection"></a>Grundlagen der Garbage Collection

In der Common Language Runtime (CLR) dient der Garbage Collector als automatischer Speicher-Manager. Der Garbage Collector bietet folgende Vorteile:

* Ermöglicht es Ihnen, eine Anwendung zu entwickeln, ohne den Speicher freigeben zu müssen. 

* Ordnet dem verwalteten Heap effizient Objekte zu. 

* Gibt Objekte frei, die nicht mehr verwendet werden, löscht den Speicher und hält Speicher für zukünftige Belegungen bereit. Verwaltete Objekte beginnen automatisch mit einem bereinigten Inhalt, damit ihre Konstruktoren nicht jedes Datenfeld initialisieren müssen.

* Bietet Speichersicherheit, indem sichergestellt wird, dass ein Objekt den Inhalt eines anderen Objekts nicht verwenden kann.


In diesem Thema werden die wichtigsten Konzepte der Garbage Collection beschrieben. Es enthält die folgenden Abschnitte:

* [Grundlagen des Arbeitsspeichers](#fundamentals-of-memory)

* [Bedingungen für eine Garbage Collection](#conditions-for-a-garbage-collection)

* [Der verwaltete Heap](#the-managed-heap)

* [Generationen](#generations)

* [Vorgänge während einer Garbage Collection](#what-happens-during-a-garbage-collection)

* [Bearbeiten von nicht verwalteten Ressourcen](#manipulating-unmanaged-resources)

## <a name="fundamentals-of-memory"></a>Grundlagen des Arbeitsspeichers

Die folgende Liste liefert eine Zusammenfassung wichtiger Arbeitsspeicherkonzepte der CLR.

* Jeder Prozess verfügt über einen eigenen separaten virtuellen Adressraum. Alle Prozesse auf demselben Computer verwenden den gleichen physischen Speicher und die gleiche Auslagerungsdatei, sofern vorhanden.

* In der Standardeinstellung verfügt jeder Prozess auf 32-Bit-Computern über einen virtuellen Adressraum von 2 GB im Benutzermodus.

* Als Anwendungsentwickler arbeiten Sie immer mit einem virtuellem Adressraum und manipulieren niemals direkt den physischen Speicher. Der Garbage Collector belegt und gibt virtuellen Arbeitsspeicher auf dem verwalteten Heap frei.

* Virtueller Arbeitsspeicher kann sich in einem von drei Zuständen befinden: 

    * Frei. Es sind keine Verweise auf den Speicherblock vorhanden, und der Speicherblock ist für eine Speicherbelegung verfügbar.

    * Reserviert. Der Speicherblock ist für die Verwendung verfügbar und kann nicht durch andere Anforderungen belegt werden. Sie können jedoch keine Daten in diesem Speicherblock speichern, bis eine Zusicherung erfolgt ist. 

    * Zugesichert. Der Speicherblock ist einem physischen Speicher zugewiesen.

* Im virtuellen Adressraum können Fragmentierungen auftreten. Das bedeutet, dass freie Blöcke (Lücken) im Adressraum vorhanden sind. Wenn eine virtuelle Speicherbelegung angefordert wird, muss der Manager für virtuellen Arbeitsspeicher einen einzelnen freien Block finden, der groß genug ist, um die Belegungsanforderung zu erfüllen. Selbst wenn 2 GB freier Speicherplatz verfügbar sind, wird die Speicherbelegung, die 2 GB angefordert hat, fehlschlagen, wenn der freie Speicherplatz nicht in einem einzelnen Adressblock verfügbar ist.

* Es kann vorkommen, dass nicht mehr genügend Arbeitsspeicher zur Verfügung steht, weil der für Belegungen verfügbare virtuelle Adressraum oder der für Zusicherungen verfügbare physische Speicher nicht mehr ausreicht.

Die Auslagerungsdatei wird auch dann verwendet, wenn der tatsächliche physische Speicherbedarf insgesamt eher niedrig ist. Wenn das erste Mal eine hohe physische Speicherauslastung auftritt, muss das Betriebssystem im physischen Speicher freien Platz für die Datenspeicherung schaffen. Zu diesem Zweck werden einige Daten aus dem physischen Speicher in die Auslagerungsdatei verschoben. Für diese Daten erfolgt solange keine neue Speicherzuordnung, bis sie tatsächlich benötigt werden. Daher können Situationen entstehen, in denen auch bei einer geringen physischen Speicherauslastung Daten in der Auslagerungsdatei abgelegt sind.

## <a name="conditions-for-a-garbage-collection"></a>Bedingungen für eine Garbage Collection

Eine Garbage Collection wird durchgeführt, wenn eine der folgenden Bedingungen zutrifft:

* Das System verfügt über einen kleinen physikalischen Speicher.

* Der Speicher, der von Objekten belegt wird, die dem verwalteten Heap zugeordnet sind, übersteigt einen akzeptablen Schwellenwert. Dieser Schwellenwert wird während der Prozessausführung kontinuierlich angepasst.

* Die [GC.Collect](xref:System.GC.Collect)-Methode wird aufgerufen. In fast allen Fällen müssen Sie diese Methode nicht aufrufen, da der Garbage Collector kontinuierlich ausgeführt wird. Diese Methode wird hauptsächlich für eindeutige Situationen und für Tests verwendet. 

## <a name="the-managed-heap"></a>Der verwaltete Heap

Nachdem der Garbage Collector von der CLR initialisiert wurde, belegt er ein Arbeitsspeichersegment für die Speicherung und Verwaltung von Objekten. Dieser Speicher wird als verwalteter Heap bezeichnet, im Gegensatz zu einem systemeigenen Heap im Betriebssystem. 

Es gibt einen verwalteten Heap für jeden verwalteten Prozess. Alle Threads im Prozess ordnen Speicher zu, für Objekte auf dem gleichen Heap.

> [!IMPORTANT]
> Die Größe der Segmente, die vom Garbage Collector zugeordnet werden, ist implementierungsspezifisch und kann jederzeit, auch in regelmäßigen Updates, geändert werden. Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen noch darf in ihr versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren. 
 
Je weniger Objekte dem Heap zugeordnet sind, desto geringer ist der Arbeitsaufwand für den Garbage Collector. Wenn Sie Objekte zuordnen, verwenden Sie keine aufgerundeten Werte, die größer sind als die tatsächlichen Anforderungen. Belegen Sie z. B. kein Array von 32 Byte, wenn Sie nur 15 Byte benötigen. 

Wenn eine Garbage Collection ausgelöst wird, gibt der Garbage Collector den Speicher frei, der von inaktiven Objekten belegt wird. Bei der Freigabe von Speicher werden aktive Objekte komprimiert, damit sie zusammen verschoben werden, und der inaktive Speicherplatz wird entfernt, sodass der Heap kleiner wird. Dadurch wird sichergestellt, dass Objekte, die gemeinsam zugeordnet wurden, auf dem verwalteten Heap zusammenbleiben, um ihre Lokalität beizubehalten.

Die Intrusivität (Häufigkeit und Dauer) von Garbage Collections wird bestimmt durch den Umfang der Speicherbelegungen und der Größe des beibehaltenen Speichers auf dem verwalteten Heap. 

Der Heap kann als Ansammlung von zwei Heaps betrachtet werden: der große Objektheap und der kleine Objektheap. 

Der große Objektheap enthält sehr große Objekte, die mindestens 85.000 Bytes groß sind. Die Objekte auf dem großen Objektheap sind normalerweise Arrays. Ein Instanzobjekt ist meistens nicht sehr groß. 

## <a name="generations"></a>Generationen

Der Heap ist in Generationen organisiert, damit er langlebige und kurzlebige Objekte behandeln kann. Die Garbage Collection tritt hauptsächlich in Verbindung mit der Freigabe kurzlebiger Objekte auf, die in der Regel nur einen kleinen Teil des Heaps belegen. Auf dem Heap gibt es drei Generationen von Objekten: 

* **Generation 0.** Dies ist die jüngste Generation, die kurzlebige Objekte enthält. Ein Beispiel für ein kurzlebiges Objekt ist eine temporäre Variable. Die Garbage Collection tritt am häufigsten in dieser Generation auf. 

  Neu zugeordnete Objekte bilden eine neue Generation von Objekten. Hierbei handelt es sich implizit um Auflistungen der Generation 0, sofern es keine großen Objekte sind. In diesem Fall gehören Sie zum großen Objektheap in einer Auflistung der Generation 2.

  Die meisten Objekte werden bei einer Garbage Collection in Generation 0 freigegeben und bleiben nicht bis zur nächsten Generation aktiv. 

* **Generation 1.** Diese Generation enthält kurzlebige Objekte und dient als Puffer zwischen kurzlebigen Objekten und langlebigen Objekten. 

* **Generation 2.** Diese Generation enthält langlebige Objekte. Ein Beispiel für ein langlebiges Objekt ist ein Objekt in einer Serveranwendung, das statische Daten enthält, die für die Dauer des Prozesses aktiv sind.

Garbage Collections finden für bestimmte Generationen statt, wenn die Bedingungen dies erfordern. Das Durchführen einer Sammlung für eine Generation bedeutet, dass Objekte in dieser Generation und in allen jüngeren Generationen gesammelt werden. Eine Garbage Collection für Generation 2 wird auch als vollständige Garbage Collection bezeichnet, da hierbei alle Objekte in allen Generationen (das heißt, alle Objekte im verwalteten Heap) freigegeben werden.

### <a name="survival-and-promotions"></a>Beibehaltene Objekte und Höherstufungen

Objekte, die bei einer Garbage Collection nicht freigegeben werden, werden als beibehaltene Objekte bezeichnet und werden auf die nächste Generation höher gestuft. Objekte, die nach einer Garbage Collection in Generation 0 noch vorhanden sind, werden auf Generation 1 höher gestuft; Objekte, die nach einer Garbage Collection in Generation 1 noch vorhanden sind, werden auf Generation 2 höher gestuft. Objekte, die nach einer Garbage Collection Generation 2 noch vorhanden sind, bleiben in Generation 2.

Wenn der Garbage Collector erkennt, dass die Rate der beibehaltenden Objekte in einer Generation hoch ist, erhöht er den Schwellenwert von Speicherbelegungen für diese Generation, sodass bei der nächsten Garbage Collection eine beträchtliche Menge an Speicher freigegeben wird. Die CLR wägt ständig zwei Prioritäten gegeneinander ab: Zum einen soll das Workingset einer Anwendung nicht zu groß werden, und zum anderen soll die Garbage Collection nicht zu viel Zeit in Anspruch nehmen.

### <a name="ephemeral-generations-and-segments"></a>Kurzlebige Generationen und Segmente

Da Objekte in der Generation 0 und 1 kurzlebig sind, werden diese Generationen als kurzlebige Generationen bezeichnet. 

Kurzlebige Generationen müssen das Speichersegment belegen, das als kurzlebiges Segment bezeichnet wird. Jedes neue vom Garbage Collector abgerufene Segment wird das neue kurzlebige Segment und enthält die Objekte, die nach einer Garbage Collection in Generation 0 noch bestehen. Das alte kurzlebige Segment wird das neue Segment der Generation 2. 


Das kurzlebige Segment kann Objekte der Generation 2 einschließen. Objekte der Generation 2 können mehrere Segmente verwenden (so viele, wie der Prozess erfordert und für den Speicher vorgesehen sind). 

Die Menge an Speicher, der bei einer kurzlebigen Garbage Collection freigegeben wird, ist auf die Größe des kurzlebigen Segments beschränkt. Der Umfang des freigegebenen Speichers ist proportional zum Speicherplatz, der von den inaktiven Objekten belegt wurde.

## <a name="what-happens-during-a-garbage-collection"></a>Was geschieht während einer Garbage Collection

Eine Garbage Collection umfasst die folgenden Phasen: 

* Eine Markierungsphase, die eine Liste aller aktiven Objekte ermittelt und erstellt.

* Eine Neuzuordnungsphase, in der die Verweise auf die zu komprimierenden Objekte aktualisiert werden. 

* Eine Komprimierungsphase, in der der von den inaktiven Objekten belegte Speicherplatz freigegeben und die noch bestehenden Objekte komprimiert werden. In der Komprimierungsphase werden die Objekte, die nach einer Garbage Collection noch vorhanden sind, zum älteren Ende des Segments verschoben. 

Da Auflistungen der Generation 2 mehrere Segmente belegen können, können Objekte, die auf Generation 2 höher gestuft werden, in ein älteres Segment verschoben werden. Objekte, die sowohl Generation 1 als auch Generation 2 überlebt haben, können in ein anderes Segment verschoben werden, da sie auf Generation 2 höher gestuft werden. 

Normalerweise wird der große Objektheap nicht komprimiert, da das Kopieren großer Objekte Leistungseinbußen zur Folge hat. Sie können jedoch die [GCSettings.LargeObjectHeapCompactionMode](xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode)-Eigenschaft verwenden, um den großen Objektheap bei Bedarf zu komprimieren. 

Der Garbage Collector bestimmt anhand folgender Informationen, ob Objekte aktiv sind: 

* **Stapelstammelemente.** Vom Just-In-Time (JIT)-Compiler bereitgestellte Stapelvariablen und Stackwalker.

* **Garbage Collection-Handles.** Diese Handles zeigen auf verwaltete Objekte und können vom Benutzercode oder der Common Language Runtime zugeordnet werden.

* **Statische Daten.** Statische Objekte in Anwendungsdomänen, die auf andere Objekte verweisen können. Jede Anwendungsdomäne verfolgt die eigenen statischen Objekte.

Vor dem Start einer Garbage Collection werden alle verwalteten Threads bis auf den Thread, der die Garbage Collection ausgelöst hat, angehalten.

Die folgende Abbildung zeigt einen Thread, der eine Garbage Collection auslöst und eine Unterbrechung der Ausführung anderer Threads verursacht.

![Garbage Collection, die durch einen Thread ausgelöst wird](./media/fundamentals/393001.png)

Ein Thread, der eine Garbage Collection auslöst

## <a name="manipulating-unmanaged-resources"></a>Bearbeiten von nicht verwalteten Ressourcen

Wenn die verwalteten Objekte mit ihren systemeigenen Dateihandles auf nicht verwaltete Objekte verweisen, müssen Sie die nicht verwalteten Objekte explizit freigeben, da der Garbage Collector den Speicher nur für den verwalteten Heap verfolgt.

Benutzer des verwalteten Objekts geben möglicherweise nicht die systemeigenen Ressourcen frei, die vom Objekt verwendet werden. Um die Bereinigung auszuführen, können Sie das verwaltete Objekt abschließen. Der Abschluss umfasst Bereinigungsaktionen, die Sie ausführen, wenn das Objekt nicht mehr verwendet wird. Wenn das verwaltete Objekt nicht mehr aktiv ist, führt es Bereinigungsaktionen aus, die in der Finalizer-Methode angegeben sind.

Wenn festgestellt wird, dass ein abzuschließendes Objekt inaktiv ist, wird der Finalizer des Objekts in eine Warteschlange eingereiht, damit die dazugehörigen Bereinigungsaktionen ausgeführt werden. Das Objekt selbst wird jedoch auf die nächste Generation höher gestuft. Daher müssen Sie bis zur nächsten Garbage Collection warten, die für diese Generation stattfindet (dies ist nicht notwendigerweise die nächste Garbage Collection), um zu bestimmen, ob das Objekt freigegeben wurde.

## <a name="see-also"></a>Siehe auch

[Garbage Collection in .NET](gc.md)



<!--HONumber=Nov16_HO3-->


