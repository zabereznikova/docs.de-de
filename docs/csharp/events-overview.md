---
title: Einführung in Ereignisse
description: Erfahren Sie in diesem Überblick etwas über Ereignisse in .NET Core und über Ziele beim Sprachentwurf für Ereignisse.
ms.date: 06/20/2016
ms.assetid: 9b8d2a00-1584-4a5b-8994-5003d54d8e0c
ms.openlocfilehash: ceae2b9319a1de9f01102987735c7db2c2883f18
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138520"
---
# <a name="introduction-to-events"></a>Einführung in Ereignisse

[Vorherige](delegates-patterns.md)

Ereignisse sind, wie Delegaten, ein Mechanismus mit *später Bindung*. In der Tat werden Ereignisse basierend auf der Sprachunterstützung für Delegaten erstellt.

Ereignisse sind eine Möglichkeit für ein Objekt (für alle interessierten Komponenten im System) weiterzugeben, dass etwas passiert ist. Jede andere Komponente kann das Ereignis abonnieren, und benachrichtigt werden, wenn ein Ereignis ausgelöst wird.

Sie haben wahrscheinlich Ereignisse in einigen ihrer Programmierungen verwendet. Viele grafische Systeme verfügen über ein Ereignismodell, um über Benutzerinteraktion zu berichten. Diese Ereignisse berichten über die Mausbewegung, das Betätigen der Schaltflächen und ähnliche Interaktionen. Dies ist eines der am häufigsten verwendeten, aber sicherlich nicht das einzige Szenario, in dem Ereignisse verwendet werden.

Sie können Ereignisse, die für Ihre Klassen ausgelöst werden sollen, definieren. Ein wichtiger Aspekt bei der Arbeit mit Ereignissen ist, dass es möglicherweise kein registriertes Objekt für ein bestimmtes Ereignis gibt. Sie müssen Ihren Code so schreiben, damit er keine Ereignisse auslöst, wenn keine Listener konfiguriert sind.

Das Abonnieren eines Ereignisses erstellt auch eine Kopplung zwischen zwei Objekten (die Ereignisquelle und die Ereignissenke). Sie müssen sicherstellen, dass sich die Ereignissenke von der Ereignisquelle abmeldet, wenn Sie nicht mehr an Ereignissen interessiert ist.

## <a name="design-goals-for-event-support"></a>Entwurfsziele für die Ereignisunterstützung

Der Sprachentwurf für Ereignisse ist auf diese Ziele ausgerichtet:

- Aktivieren Sie eine sehr geringe Kopplung zwischen der Ereignisquelle und einer Ereignissenke. Diese beiden Komponenten können nicht von derselben Organisation geschrieben werden und werden möglicherweise sogar auf völlig unterschiedliche Zeitpläne aktualisiert.

- Es sollte sehr einfach sein, ein Ereignis zu abonnieren, und sich von demselben Ereignis abzumelden.

- Ereignisquellen sollten mehrere Ereignisabonnenten unterstützen. Es sollte auch unterstützen, dass es keine angefügten Ereignisabonnenten gibt.

Sie sehen, dass die Ziele für Ereignisse, den Zielen für Delegaten sehr ähnlich sind.
Deshalb basiert die Sprachunterstützung für Ereignisse auf der Sprachunterstützung für Delegaten.

## <a name="language-support-for-events"></a>Sprachunterstützung für Ereignisse

Die Syntax zum Definieren von Ereignissen, und zum Abonnieren oder Abmelden von Ereignissen, ist eine Erweiterung der Syntax für Delegaten.

Zum Definieren eines Ereignisses verwenden Sie das `event`-Schlüsselwort:

```csharp
public event EventHandler<FileListArgs> Progress;
```

Der Typ des Ereignisses (`EventHandler<FileListArgs>` in diesem Beispiel) muss ein Delegattyp sein. Es gibt eine Reihe von Konventionen, die Sie befolgen sollten, wenn Sie ein Ereignis deklarieren. Normalerweise verfügt der Delegattyp des Ereignisses über einen „void“-Rückgabetyp.
Ereignisdeklarationen sollten ein Verb oder eine Verbalphrase sein.
Verwenden Sie die Vergangenheitsform, wenn das Ereignis meldet, dass etwas geschehen ist. Verwenden Sie ein Gegenwartsverb (z.B. `Closing`) um etwas zu melden, das geschehen wird. Häufig gibt die Verwendung der Gegenwartsform an, dass die Klasse eine Art der Anpassung des Verhaltens unterstützt. Eines der häufigsten Szenarios ist die Unterstützung des Abbruchs. Angenommen, ein `Closing`-Ereignis enthält ein Argument, das angeben würde, ob der Schließvorgang fortgesetzt werden soll oder nicht.  Andere Szenarios ermöglichen es Aufrufern, das Verhalten zu ändern, indem die Eigenschaften der Ereignisargumente aktualisiert werden. Sie können ein Ereignis auslösen, um eine vorgeschlagene nächste Aktion anzugeben, die einen Algorithmus auslösen wird. Der Ereignishandler kann eine andere Aktion vorgeben, indem er die Eigenschaften des Ereignisarguments ändert.

Wenn Sie das Ereignis auslösen möchten, rufen Sie mithilfe der Aufrufsyntax des Delegaten den Ereignishandler auf:

```csharp
Progress?.Invoke(this, new FileListArgs(file));
```

Wie im Abschnitt unter [Delegaten](delegates-patterns.md) beschrieben, macht der ?.
Operator es leicht, sicherzustellen, dass Sie nicht versuchen das Ereignis auszulösen, wenn keine Abonnenten für dieses Ereignis vorhanden sind.
 
Sie abonnieren ein Ereignis mithilfe des `+=`-Operators:

```csharp
EventHandler<FileListArgs> onProgress = (sender, eventArgs) => 
    Console.WriteLine(eventArgs.FoundFile);

fileLister.Progress += onProgress;
```

Die Handlermethode weist in der Regel das Präfix „On“ auf, gefolgt vom Ereignisnamen, wie oben gezeigt.

Sie melden sich mithilfe des `-=`-Operators ab:

```csharp
fileLister.Progress -= onProgress;
```

Es ist wichtig, zu beachten, dass ich eine lokale Variable für den Ausdruck deklariert habe, der den Ereignishandler darstellt. Damit wird sichergestellt, dass UNSUBSCRIBE den Handler entfernt.
Wenn Sie stattdessen den Text des Lambdaausdrucks verwendet haben, versuchen Sie einen Handler, der nicht angefügt wurde und nichts tut, zu entfernen.

Im nächsten Artikel erfahren Sie mehr über das typische Ereignismuster und verschiedene Varianten dieses Beispiels.

[Nächste](event-pattern.md)
