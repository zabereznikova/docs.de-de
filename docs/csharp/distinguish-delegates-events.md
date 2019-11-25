---
title: Unterscheidung zwischen Delegaten und Ereignissen
description: Informationen zum Unterschied zwischen Delegaten und Ereignissen und wann diese Features jeweils in .NET Core verwendet werden.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 0fdc8629-2fdb-4a7c-a433-5b9d04eaf911
ms.openlocfilehash: ff90af1d2b1a92f06eed58228f8e8ca5ff6b93ca
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73037318"
---
# <a name="distinguishing-delegates-and-events"></a>Unterscheidung zwischen Delegaten und Ereignissen

[Vorherige](modern-events.md)

Entwickler, die die .NET Core-Plattform noch nicht kennen, haben oft mit der Entscheidung zwischen einem Entwurf auf der Grundlage von `delegates` und einem Entwurf auf der Grundlage von `events` zu kämpfen. Dies ist ein schwieriges Konzept, da die zwei Sprachfunktionen sehr ähnlich sind. Ereignisse werden sogar mithilfe der Sprachunterstützung für Delegaten erstellt. 

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

## <a name="event-listeners-often-have-longer-lifetimes"></a>Ereignislistener haben häufig eine längere Lebensdauer 

Dies ist eine etwas schwächere Begründung. Jedoch können Sie feststellen, dass ereignisbasierte Entwürfe natürlicher sind, wenn die Ereignisquelle über einen langen Zeitraum Ereignisse auslösen wird. Sie können Beispiele dafür für UX-Steuerelemente auf vielen Systemen finden. Sobald Sie ein Ereignis abonnieren, kann die Ereignisquelle Ereignisse während der gesamten Lebensdauer des Programms auslösen.
(Sie können das Abonnement von Ereignissen kündigen, wenn Sie sie nicht mehr benötigen.)

Vergleichen Sie das mit vielen delegatbasierten Entwürfen, bei denen ein Delegat als Argument an eine Methode verwendet wird, und der Delegat wird nicht verwendet, nachdem diese Methode zurückgegeben wird.

## <a name="evaluate-carefully"></a>Sorgfältig bewerten

Die oben genannten Aspekte sind keine verbindlichen Regeln. Stattdessen stellen sie Leitfäden dar, mit denen Sie entscheiden können, welche Auswahl für Ihre spezielle Verwendung am besten geeignet ist. Da sie sich ähneln, können Sie sogar beide als Prototyp nutzen, und überlegen, welche beim Arbeiten natürlicher wäre. Beide behandeln Szenarios mit später Bindung gut. Verwenden Sie die, die Ihren Entwurf am besten kommuniziert.
