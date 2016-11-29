---
title: "Übersicht über BlockingCollection"
description: "Übersicht über BlockingCollection"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a1a867de-53c2-49ca-9a1a-e5770a942724
translationtype: Human Translation
ms.sourcegitcommit: e07788926a995b41571be276379ad9285747951d
ms.openlocfilehash: 64a01b5e21e012dfaae07a02f5fb27932be9cf98

---

# <a name="blockingcollection-overview"></a>Übersicht über BlockingCollection

[BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) ist eine threadsichere Auflistungsklasse, die die folgenden Features bietet:

*   Eine Implementierung des Producer-Consumer-Musters.

*   Threadsicheres Hinzufügen und Entfernen von Elementen aus einer Auflistung.

*   Optionale maximale Kapazität.

*   Einfüge- und Löschvorgänge, die blockiert werden, wenn die Auflistung leer oder voll ist.

*   „Versuchs“-Einfüge- und Löschvorgänge, die nicht oder nur für eine angegebene Zeitspanne blockiert werden.

*   Kapselt jeden Auflistungstyp, der [IProducerConsumerCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.IProducerConsumerCollection-1) implementiert.

*   Abbruch mit Abbruchtoken.

*   Zwei Arten von Enumerationen mit `foreach`: 

    1. Schreibgeschützte Enumeration.
    
    2. Enumeration, in deren Verlauf Elemente entfernt werden.
    
## <a name="bounding-and-blocking-support"></a>Unterstützung von Begrenzen und Blockieren 

[BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) unterstützt Begrenzen und Blockieren. Begrenzen bedeutet, dass Sie die maximale Kapazität der Auflistung festlegen können. Begrenzen ist in bestimmten Szenarien wichtig, da es Ihnen ermöglicht, die maximale Größe der Auflistung im Arbeitsspeicher zu steuern, und es verhindert, dass die erzeugenden Threads sich zu weit vor die verbrauchenden Threads bewegen.

Mehrere Threads oder Tasks können gleichzeitig der Auflistung Elemente hinzufügen, und wenn die Auflistung die angegebene maximale Kapazität erreicht, werden die erzeugenden Threads blockiert, bis ein Element entfernt wird. Mehrere Consumer können gleichzeitig Elemente entfernen, und wenn die Auflistung leer ist, werden die verbrauchenden Threads blockiert, bis ein Producer ein Element hinzufügt. Ein Producer-Thread kann `CompleteAdding` aufrufen, um anzuzeigen, dass keine Elemente mehr hinzugefügt werden. Consumer überwachen die `IsCompleted`-Eigenschaft, um zu wissen, wann die Auflistung leer ist, und keine Elemente mehr hinzugefügt werden. Das folgende Beispiel zeigt eine einfache `BlockingCollection` mit einer begrenzten Kapazität von 100. Ein Producer-Task fügt der Auflistung Elemente hinzu, solange eine externe Bedingung wahr ist, und ruft dann `CompleteAdding` auf. Der Consumer-Task entnimmt Elemente, bis die `IsCompleted`-Eigenschaft wahr ist.

```csharp
// A bounded collection. It can hold no more 
// than 100 items at once.
BlockingCollection<Data> dataItems = new BlockingCollection<Data>(100);


// A simple blocking consumer with no cancellation.
Task.Run(() => 
{
    while (!dataItems.IsCompleted)
    {

        Data data = null;
        // Blocks if number.Count == 0
        // IOE means that Take() was called on a completed collection.
        // Some other thread can call CompleteAdding after we pass the
        // IsCompleted check but before we call Take. 
        // In this example, we can simply catch the exception since the 
        // loop will break on the next iteration.
        try
        {
            data = dataItems.Take();
        }
        catch (InvalidOperationException) { }

        if (data != null)
        {
            Process(data);
        }
    }
    Console.WriteLine("\r\nNo more items to take.");
});

// A simple blocking producer with no cancellation.
Task.Run(() =>
{
    while (moreItemsToAdd)
    {
        Data data = GetData();
        // Blocks if numbers.Count == dataItems.BoundedCapacity
        dataItems.Add(data);
    }
    // Let consumer know we are done.
    dataItems.CompleteAdding();
});
```

Ein vollständiges Beispiel finden Sie unter [Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection](how-to-add-and-take-items.md).

## <a name="timed-blocking-operations"></a>Zeitgesteuerte Blockierungsvorgänge

In zeitgesteuerten `TryAdd`- und `TryTake`-Blockierungsvorgängen, die für begrenzte Sammlungen durchgeführt werden, versucht die Methode, ein Element hinzuzufügen oder zu entnehmen. Wenn ein Element verfügbar ist, wird es in der Variablen platziert, die als Verweis übergeben wurde, und die Methode gibt `true` zurück. Wenn nach einer angegebenen Timeoutfrist kein Element abgerufen wird, gibt die Methode `false` zurück. Der Thread ist dann vor dem erneuten Versuch, auf die Auflistung zuzugreifen, frei für andere nützliche Aufgaben. Ein Beispiel für das zeitgesteuerte Blockieren des Zugriffs ist das zweite Beispiel unter [Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection](how-to-add-and-take-items.md).

## <a name="cancelling-add-and-take-operations"></a>Abbrechen von Hinzufüge- und Nehmevorgängen

Hinzufüge- und Nehmevorgänge werden in der Regel in einer Schleife ausgeführt. Sie können eine Schleife durch die Übergabe eines `CancellationToken` an die `TryAdd`- oder `TryTake`-Methode abbrechen und dann den Wert der `IsCancellationRequested`-Eigenschaft des Tokens in jeder Iteration überprüfen. Wenn der Wert `true` ist, liegt es an Ihnen, mit Bereinigen aller Ressourcen und Beenden der Schleife auf die Abbruchanforderung zu reagieren. Das folgende Beispiel zeigt eine Überladung von `TryAdd`, die ein Abbruchtoken entgegennimmt, und den Code, der es verwendet:

```csharp
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );
```

## <a name="specifying-the-collection-type"></a>Angeben des Auflistungstyps

Beim Erstellen einer `BlockingCollection<T>;` können Sie nicht nur die begrenzte Kapazität angeben, sondern auch den Typ der zu verwendenden Auflistung. Sie könnten z.B. einen [ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) für das First-in-First-out-Verhalten (FIFO) oder einen [ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) für das Last-in-First-out-Verhalten (LIFO) angeben. Sie können jede Auflistungsklasse verwenden, die die [IProducerConsumerCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.IProducerConsumerCollection-1)-Schnittstelle implementiert. Der standardmäßige Auflistungstyp für `BlockingCollection<T>` ist `ConcurrentQueue<T>`. Das folgende Codebeispiel veranschaulicht das Erstellen einer `BlockingCollection<T>` von Zeichenfolgen, die eine Kapazität von 1.000 hat und einen [ConcurrentBag&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentBag-1) verwendet:

```csharp
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );
```

## <a name="ienumerable-support"></a>IEnumerable-Unterstützung

`BlockingCollection<T>` bietet eine `GetConsumingEnumerable`-Methode, mit der Consumer eine `foreach`-Anweisung verwenden können, um Elemente zu entfernen, bis die Sammlung abgeschlossen ist, d.h. bis sie leer ist und keine Elemente mehr hinzugefügt werden. Weitere Informationen finden Sie unter [Gewusst wie: Entfernen von Elementen in einer BlockingCollection mit ForEach](how-to-use-foreach-to-remove.md).

## <a name="using-many-blockingcollections-as-one"></a>Verwenden vieler BlockingCollections als eine einzige

Für Szenarien, in denen ein Consumer Elemente aus mehreren Auflistungen gleichzeitig nehmen muss, können Sie Arrays von `BlockingCollection<T>` erstellen und statische Methoden wie `TakeFromAny` und `AddToAny` verwenden, die Elemente beliebigen Auflistungen im Array hinzufügen bzw. daraus entnehmen. Wenn eine Auflistung blockiert wird, versucht die Methode sofort, eine andere zu verwenden, bis sie eine findet, die den Vorgang ausführen kann. Weitere Informationen finden Sie unter [Gewusst wie: Verwenden von Arrays mit blockierenden Auflistungen in einer Pipeline](how-to-use-arrays-of-blockingcollections.md).

## <a name="see-also"></a>Siehe auch

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)

[Sammlungen und Datenstrukturen](../index.md)

[Threadsichere Sammlungen](index.md)




<!--HONumber=Nov16_HO3-->


