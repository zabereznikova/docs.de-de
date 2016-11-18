---
title: Garbage Collection
description: Garbage Collection
keywords: .NET, .NET Core
author: richlander
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: db39a0f5-e363-490f-a7e6-adb9a6ff2a8c
translationtype: Human Translation
ms.sourcegitcommit: 213ce098bcc2b5e31c55e759d895254d5ca33caa
ms.openlocfilehash: c040a992b91ae27398264709aaa31440cea677f5

---

# <a name="garbage-collection"></a>Garbage Collection

Die Garbage Collection ist eines der wichtigsten Features der .NET-Plattform für verwalteten Code. Der Garbage Collector (GC) verwaltet die Zuweisung und Freigabe von Arbeitsspeicher für Sie. Sie müssen den Arbeitsspeicher nicht selbst zuweisen oder freigeben oder die Lebensdauer der Objekte verwalten, die diesen Speicher verwenden. Eine Zuweisung erfolgt jedes Mal, wenn Sie ein _neues_ Objekt erstellen oder ein Werttyp geschachtelt wird. Zuweisungen erfolgen in der Regel sehr schnell. Wenn nicht genügend Arbeitsspeicher vorhanden ist, um ein Objekt zuzuweisen, muss der Garbage Collector veraltete Objekte und Datenfragmente sammeln und löschen, um Arbeitsspeicher für neue Zuweisungen freizugeben. Dieser Vorgang wird als „Garbage Collection“ bezeichnet.

Der Garbage Collector dient als automatischer Speicher-Manager. Der Garbage Collector bietet folgende Vorteile:

*   Ermöglicht es Ihnen, eine Anwendung zu entwickeln, ohne den Speicher freigeben zu müssen.
*   Ordnet dem verwalteten Heap effizient Objekte zu.
*   Gibt Objekte frei, die nicht mehr verwendet werden, löscht den Speicher und hält Speicher für zukünftige Belegungen bereit. Verwaltete Objekte beginnen automatisch mit einem bereinigten Inhalt, damit ihre Konstruktoren nicht jedes Datenfeld initialisieren müssen.
*   Bietet Speichersicherheit, indem sichergestellt wird, dass ein Objekt den Inhalt eines anderen Objekts nicht verwenden kann.

Der .NET-Garbage Collector ist generationsbasiert und umfasst drei Generationen. Jede Generation verfügt über einen eigenen Heap, der zum Speichern zugewiesener Objekte verwendet wird. Ein Grundprinzip lautet, dass die meisten Objekte entweder kurzlebig oder langlebig sind. In Generation 0 werden Objekte zuerst zugewiesen. Objekte überstehen häufig die erste Generation nicht, da sie zum Zeitpunkt der nächsten Garbage Collection nicht mehr verwendet werden (sich außerhalb des gültigen Bereichs befinden). In Generation 0 erfolgt die Auflistung schnell, da der entsprechende Heap klein ist. Generation 1 ist gewissermaßen eine zweite Chance. Objekte, die kurzlebig sind, aber die Auflistung in Generation 0 überstehen (häufig aufgrund eines zufälligen Timings) wechseln zu Generation 1\.Auch in Generation 1 erfolgen Auflistungen schnell, da der entsprechende Heap ebenfalls klein ist. Die ersten beiden Heaps bleiben klein, da die Objekte entweder gesammelt oder in den Heap der nächsten Generation heraufgestuft werden. In Generation 2 befinden sich alle langlebigen Objekte. Der Heap für Generation 2 kann sehr groß werden, da die darin enthaltenen Objekte sehr langlebig sein können und es keine Generation 3 gibt, in die Objekte heraufgestuft werden können.

Der GC verfügt über einen zusätzlichen Heap für große Objekte, den Large Object Heap (LOH). Dieser ist für Objekte mit einer Größe von 85.000 Bytes oder mehr reserviert. Ein großes Objekt wäre z.B. ein Bytearray (Byte[]) mit 85.000 Elementen. Große Objekte werden nicht den generationsbasierten Heaps, sondern direkt dem LOH zugewiesen.

Auflistungen in Generation 2 und LOH können bei Programmen, die bereits sehr lange ausgeführt werden oder große Datenmengen verarbeiten, einen langen Zeitraum beanspruchen. Bei großen Serverprogrammen sind Heaps in der Größenordnung von mehreren Dutzend GB keine Seltenheit. Der GC verwendet verschiedene Techniken, um den Zeitraum zu verkürzen, während dessen die Programmausführung blockiert wird. Der primäre Ansatz hierbei ist, so viel Garbage Collection-Vorgänge wie möglich in einem Hintergrundthread und in einer Weise auszuführen, die die Programmausführung nicht beeinträchtigt. Der GC bietet auch Entwicklern einige Möglichkeiten, sein Verhalten zu beeinflussen – was zur Verbesserung der Leistung sehr nützlich sein kann.

## <a name="related-topics"></a>Verwandte Themen

Titel | Beschreibung
----- | ----------- 
[Automatische Speicherverwaltung und Garbage Collection](gc.md) | Einführung in die grundlegenden Konzepte der Speicherverwaltung in .NET
[Grundlagen der Garbage Collection](fundamentals.md) | Beschreibt, wie die Garbage Collection funktioniert, wie Objekte auf dem verwalteten Heap zugeordnet werden und erläutert andere Kernkonzepte.
[Indizierte Auflistungen](induced.md) | Beschreibt, wie eine Garbage Collection initiiert wird.
[Latenzmodi](latency.md) | Beschreibt die Modi, die das Ausmaß der Garbage Collection bestimmen.
[Schwache Verweise](weak-references.md) | Beschreibt Funktionen, die dem Garbage Collector ermöglichen, ein Objekt zu sammeln, während die Anwendung nach wie vor auf das Objekt zugreifen kann.
 
## <a name="reference"></a>Verweis

[System.GC](xref:System.GC)

[System.GCCollectionMode](xref:System.GCCollectionMode)

[System.Runtime.GCLatencyMode](xref:System.Runtime.GCLatencyMode)

[System.Runtime.GCSettings](xref:System.Runtime.GCSettings)

[GCSettings.LargeObjectHeapCompactionMode](xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode)

[Object.Finalize](xref:System.Object.Finalize)

[System.IDisposable](xref:System.IDisposable)

## <a name="see-also"></a>Siehe auch

[Bereinigen von nicht verwalteten Ressourcen](unmanaged.md)




<!--HONumber=Nov16_HO3-->


