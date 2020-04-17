---
title: Unterschiede zwischen Delegaten und Ereignissen
description: Informationen zum Unterschied zwischen Delegaten und Ereignissen und wann diese Features jeweils in .NET Core verwendet werden.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 0fdc8629-2fdb-4a7c-a433-5b9d04eaf911
ms.openlocfilehash: 51d982c9b5b16a5fc28ede5f0318bc100bb33b68
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805764"
---
# <a name="distinguishing-delegates-and-events"></a>Unterscheidung zwischen Delegaten und Ereignissen

[Vorherige](modern-events.md)

Entwickler, die die .NET Core-Plattform noch nicht kennen, haben oft mit der Entscheidung zwischen einem Entwurf auf der Grundlage von `delegates` und einem Entwurf auf der Grundlage von `events` zu kämpfen. Die Wahl zwischen Delegaten oder Ereignissen ist meist schwierig, da sich die beiden Sprachfeatures ähneln. Ereignisse werden sogar mithilfe der Sprachunterstützung für Delegaten erstellt.

Beide bieten ein Szenario mit später Bindung: Sie ermöglichen Szenarios, in denen eine Komponente durch Aufrufen einer Methode, die nur zur Laufzeit bekannt ist, kommuniziert. Beide Versionen unterstützen einzelne und mehrerer Methoden des Abonnenten. Möglicherweise finden Sie dies unter der Bezeichnung Singlecast- und Multicast-Unterstützung. Beide unterstützen eine ähnliche Syntax zum Hinzufügen und Entfernen von Handlern. Schließlich verwenden das Auslösen eines Ereignisses und das Aufrufen eines Delegaten genau die gleiche Methodensyntax zu Aufrufen. Auch unterstützen beide die gleiche `Invoke()`-Methodensyntax für die Verwendung mit dem `?.`-Operator.

Mit all diesen Ähnlichkeiten ist es einfach nur schwer zu bestimmen, wann welche Komponente benutzt werden soll.

## <a name="listening-to-events-is-optional"></a>Das Überwachen von Ereignissen ist optional

Der wichtigste Aspekt bei der Bestimmung, welche Sprachfunktion verwendet werden soll, ist die Frage, ob ein angefügter Abonnent vorhanden sein muss. Wenn der Code den Code vom Abonnenten aufrufen muss, sollten Sie einen Entwurf basierend auf den Delegaten verwenden. Wenn Ihr Code all seine Arbeit ohne Aufruf von Abonnenten abschließen kann, sollten Sie einen Entwurf auf Grundlage von Ereignissen verwenden.

Betrachten Sie die Beispiele, die während dieses Abschnitts erstellt wurden. Dem Code, den Sie mithilfe von `List.Sort()` erstellt haben, muss eine Vergleichsfunktion gegeben werden, um die Elemente ordnungsgemäß zu sortieren. LINQ-Abfragen müssen mit Delegaten bereitgestellt werden, um zu bestimmen, welche Elemente zurückgeben werden sollen. Beide verwenden einen mit Delegaten erstellten Entwurf.

Betrachten Sie das `Progress`-Ereignis. Es meldet den Status eines Tasks.
Der Task wird fortgesetzt, unabhängig davon, ob alle Listener vorhanden sind.
Der `FileSearcher` ist ein weiteres Beispiel. Es würde weiterhin alle gesuchten Dateien suchen und finden, auch ohne angefügte Ereignisabonnenten.
UX-Steuerelemente funktionieren weiterhin ordnungsgemäß, auch wenn keine Abonnenten die Ereignisse überwachen. Beide verwenden Entwürfe auf der Grundlage von Ereignissen.

## <a name="return-values-require-delegates"></a>Rückgabewerte erfordern Delegaten

Ein weiterer Aspekt ist der Methodenprototyp, den Sie für die Delegatmethode haben sollten. Wie Sie gesehen haben, verfügen die für Ereignisse verwendete Delegaten alle über einen void-Rückgabetyp. Sie haben auch gesehen, dass Ausdrücke vorhanden sind, um Ereignishandler zu erstellen, die Informationen durch Ändern der Eigenschaften des Ereignisargumentobjekts zurück an die Ereignisquellen geben. Während diese Ausdrücke funktionieren, sind sie nicht so natürlich wie die Rückgabe eines Werts aus einer Methode.

Beachten Sie, dass häufig diese beiden Heuristiken vorhanden sein können: Wenn die Delegatmethode einen Wert zurückgibt, wirkt sich dies wahrscheinlich auf irgendeine Weise auf den Algorithmus aus.

## <a name="events-have-private-invocation"></a>Privater Aufruf von Ereignissen

Klassen, in denen das Ereignis nicht enthalten ist, können nur Ereignislistener hinzufügen und entfernen. Nur die Klasse, die das Ereignis enthält, kann das Ereignis aufrufen. Ereignisse sind normalerweise öffentliche Klassenmember.
Delegaten hingegen werden oft als Parameter übergeben und als private Klassenmember gespeichert, sofern sie überhaupt gespeichert werden.

## <a name="event-listeners-often-have-longer-lifetimes"></a>Ereignislistener haben häufig eine längere Lebensdauer

Dass Ereignislistener eine längere Lebensdauer besitzen, ist eine eher schlechtere Begründung. Jedoch können Sie feststellen, dass ereignisbasierte Entwürfe natürlicher sind, wenn die Ereignisquelle über einen langen Zeitraum Ereignisse auslösen wird. Beispiele für ereignisbasierte Designs für Steuerelemente der Benutzeroberfläche können Sie in vielen Systemen finden. Sobald Sie ein Ereignis abonnieren, kann die Ereignisquelle Ereignisse während der gesamten Lebensdauer des Programms auslösen.
(Sie können das Abonnement von Ereignissen kündigen, wenn Sie sie nicht mehr benötigen.)

Vergleichen Sie das mit vielen delegatbasierten Entwürfen, bei denen ein Delegat als Argument an eine Methode verwendet wird, und der Delegat wird nicht verwendet, nachdem diese Methode zurückgegeben wird.

## <a name="evaluate-carefully"></a>Sorgfältig bewerten

Die oben genannten Aspekte sind keine verbindlichen Regeln. Stattdessen stellen sie Leitfäden dar, mit denen Sie entscheiden können, welche Auswahl für Ihre spezielle Verwendung am besten geeignet ist. Da sie sich ähneln, können Sie sogar beide als Prototyp nutzen, und überlegen, welche beim Arbeiten natürlicher wäre. Beide behandeln Szenarios mit später Bindung gut. Verwenden Sie die, die Ihren Entwurf am besten kommuniziert.
