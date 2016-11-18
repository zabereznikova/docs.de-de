---
title: 'Gewusst wie: Entfernen von Elementen in einer BlockingCollection mit ForEach'
description: 'Gewusst wie: Entfernen von Elementen in einer BlockingCollection mit ForEach'
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: f3db5825-b5c9-4e8b-80bc-e11760d9523e
translationtype: Human Translation
ms.sourcegitcommit: c15f2da15c6448cf1c36dea2d5fd53e734bb6608
ms.openlocfilehash: 98a01aaebb209fe80b3c1270295399e5914cbd09

---

# <a name="how-to-use-foreach-to-remove-items-in-a-blockingcollection"></a>Gewusst wie: Entfernen von Elementen in einer BlockingCollection mit ForEach

Zusätzlich zum Entnehmen von Elementen aus einer [BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) mithilfe der Methoden `Take` und `TryTake` können Sie auch eine `foreach`-Schleife verwenden, um Elemente zu entfernen, bis der Hinzufügevorgang abgeschlossen und die Auflistung leer ist. Dies wird als mutierende oder verbrauchende Enumeration bezeichnet, da dieser Enumerator, im Gegensatz zu einer typischen `foreach`-Schleife, die Quellauflistung durch Entfernen von Elementen verändert.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt das Entfernen aller Elemente in einer `BlockingCollection<T>` mithilfe einer `foreach`-Schleife. 

```csharp
using System;
using System.Collections.Concurrent;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

class Example
{
   // Limit the collection size to 2000 items at any given time.
   // Set itemsToProduce to > 500 to hit the limit.
   const int upperLimit = 1000;

   // Adjust this number to see how it impacts the producing-consuming pattern.
   const int itemsToProduce = 100;

   static BlockingCollection<long> collection = new BlockingCollection<long>(upperLimit);

   // Variables for diagnostic output only.
   static Stopwatch sw = new Stopwatch();
   static int totalAdditions = 0;

   // Counter for synchronizing producers.
   static int producersStillRunning = 2;

   static void Main()
   {
       // Start the stopwatch.
       sw.Start();

       // Queue the Producer threads. Store in an array
       // for use with ContinueWhenAll
       Task[] producers = new Task[2];
       producers[0] = Task.Run(() => RunProducer("A", 0));
       producers[1] = Task.Run(() => RunProducer("B", itemsToProduce));

       // Create a cleanup task that will call CompleteAdding after
       // all producers are done adding items.
       Task cleanup = Task.Factory.ContinueWhenAll(producers, (p) => collection.CompleteAdding());

       // Queue the Consumer thread. Put this call
       // before Parallel.Invoke to begin consuming as soon as
       // the producers add items.
       Task.Run(() => RunConsumer());

       // Keep the console window open while the
       // consumer thread completes its output.
       Console.ReadKey(true);
   }

   static void RunProducer(string ID, int start)
   {

       int additions = 0;
       for (int i = start; i < start + itemsToProduce; i++)
       {
           // The data that is added to the collection.
           long ticks = sw.ElapsedTicks;

           // Display additions and subtractions.
           Console.WriteLine("{0} adding tick value {1}. item# {2}", ID, ticks, i);

           if(!collection.IsAddingCompleted)
               collection.Add(ticks);

           // Counter for demonstration purposes only.
           additions++;

           // Uncomment this line to
           // slow down the producer threads     ing.
           Thread.SpinWait(100000);
       }

       Interlocked.Add(ref totalAdditions, additions);
       Console.WriteLine("{0} is done adding: {1} items", ID, additions);
   }

   static void RunConsumer()
   {
       // GetConsumingEnumerable returns the enumerator for the
       // underlying collection.
       int subtractions = 0;
       foreach (var item in collection.GetConsumingEnumerable())
       {
           Console.WriteLine("Consuming tick value {0} : item# {1} : current count = {2}",
                   item.ToString("D18"), subtractions++, collection.Count);
       }

       Console.WriteLine("Total added: {0} Total consumed: {1} Current count: {2} ",
                           totalAdditions, subtractions, collection.Count);
       sw.Stop();

       Console.WriteLine("Press any key to exit");
   }
}

```

Dieses Beispiel verwendet eine `foreach`-Schleife mit der `BlockingCollection<T>.GetConsumingEnumerable`-Methode im verbrauchenden Thread, wodurch jedes Element beim Aufzählen aus der Auflistung entfernt wird. `BlockingCollection<T>` begrenzt die maximale Anzahl von Elementen, die sich zu einem bestimmten Zeitpunkt in der Sammlung befinden können. Durch Aufzählen der Auflistung auf diese Weise wird der Consumerthread blockiert, wenn keine Elemente verfügbar sind oder die Auflistung leer ist. In diesem Beispiel ist eine Blockierung kein Problem, da der Producerthread Elemente schneller hinzufügt als sie verbraucht werden können. 

Es gibt keine Garantie dafür, dass die Elemente in der gleichen Reihenfolge aufgezählt werden, in der sie von den Producerthreads hinzugefügt werden.

Um die Auflistung aufzuzählen, ohne sie zu verändern, verwenden Sie einfach `foreach` ohne die `GetConsumingEnumerable`-Methode. Es ist jedoch wichtig zu wissen, dass diese Art der Enumeration eine Momentaufnahme der Auflistung zu einem genauen Zeitpunkt darstellt. Wenn weitere Threads gleichzeitig Elemente hinzufügen oder entfernen, während die Schleife ausgeführt wird, stellt die Schleife möglicherweise nicht den tatsächlichen Zustand der Auflistung dar.

## <a name="see-also"></a>Siehe auch

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)

[Übersicht über BlockingCollection](blockingcollection-overview.md)



<!--HONumber=Nov16_HO3-->


