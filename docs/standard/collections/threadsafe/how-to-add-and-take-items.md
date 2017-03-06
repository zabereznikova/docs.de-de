---
title: "Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection"
description: "Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection"
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 2b9d39ab-0993-4453-b021-b04870098bf7
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: e560eb44f783aaa50ec335df4f3171090d238f32
ms.lasthandoff: 03/03/2017

---

# <a name="how-to-add-and-take-items-individually-from-a-blockingcollection"></a>Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection

Dieses Beispiel zeigt, wie einer [BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) Elemente sowohl auf blockierende als auch auf nicht blockierende Weise hinzugefügt und ebenso daraus entfernt werden können. Weitere Informationen zu `BlockingCollection<T>` finden Sie unter [Übersicht über BlockingCollection](blockingcollection-overview.md). 

Ein Beispiel für das Entfernen von Elementen aus einer `BlockingCollection<T>` per Enumeration, bis sie leer ist und keine weiteren Elemente hinzugefügt werden, finden Sie unter [Gewusst wie: Entfernen von Elementen in einer BlockingCollection mit ForEach](how-to-use-foreach-to-remove.md).

## <a name="example"></a>Beispiel

```csharp
using System;
using System.Collections.Concurrent;
using System.Threading;
using System.Threading.Tasks;

class Program
{
   static void Main()
   {
      // Increase or decrease this value as desired.
      int itemsToAdd = 500;

      // Preserve all the display output for Adds and Takes
      Console.SetBufferSize(80, (itemsToAdd * 2) + 3);

      // A bounded collection. Increase, decrease, or remove the
      // maximum capacity argument to see how it impacts behavior.
      BlockingCollection<int> numbers = new BlockingCollection<int>(50);


      // A simple blocking consumer with no cancellation.
      Task.Run(() =>
      {
          int i = -1;
          while (!numbers.IsCompleted)
          {
              try
              {
                  i = numbers.Take();
              }
              catch (InvalidOperationException)
              {
                  Console.WriteLine("Adding was completed!");
                  break;
              }
              Console.WriteLine("Take:{0} ", i);

              // Simulate a slow consumer. This will cause
              // collection to fill up fast and thus Adds will block.
              Thread.SpinWait(100000);
          }

          Console.WriteLine("\r\nNo more items to take. Press the Enter key to exit.");
      });

      // A simple blocking producer with no cancellation.
      Task.Run(() =>
      {
          for (int i = 0; i < itemsToAdd; i++) {
              numbers.Add(i);
              Console.WriteLine("Add:{0} Count={1}", i, numbers.Count);
          }

          // See documentation for this method.
          numbers.CompleteAdding();
      });

      // Keep the console display open in debug mode.
      Console.ReadLine();
   }
}

```

## <a name="example"></a>Beispiel

In diesem zweiten Beispiel wird veranschaulicht, wie Elemente hinzuzufügen bzw. zu entnehmen sind, damit die Vorgänge nicht blockiert werden. Wenn kein Element vorhanden, die maximale Kapazität in einer begrenzten Auflistung erreicht oder der Timeoutzeitraum abgelaufen ist, gibt der `TryAdd`-Vorgang oder der `TryTake`-Vorgang „false“ zurück. Dies ermöglicht dem Thread, vorübergehend eine andere Aufgabe zu erledigen und später erneut zu versuchen, entweder ein neues Element abzurufen oder das Element hinzuzufügen, das zuvor nicht hinzugefügt werden konnte. Das Programm veranschaulicht außerdem, wie für den Zugriff auf eine `BlockingCollection<T>` ein Abbruch implementiert wird.

```csharp
using System;
using System.Collections.Concurrent;
using System.Threading;
using System.Threading.Tasks;

class ProgramWithCancellation
{

    static int inputs = 2000;

    static void Main()
    {
        // The token source for issuing the cancelation request.
        CancellationTokenSource cts = new CancellationTokenSource();

        // A blocking collection that can hold no more than 100 items at a time.
        BlockingCollection<int> numberCollection = new BlockingCollection<int>(100);

        // Set console buffer to hold our prodigious output.
        Console.SetBufferSize(80, 2000);

        // The simplest UI thread ever invented.
        Task.Run(() =>
        {
            if (Console.ReadKey(true).KeyChar == 'c')
                cts.Cancel();
        });

        // Start one producer and one consumer.
        Task t1 = Task.Run(() => NonBlockingConsumer(numberCollection, cts.Token));
        Task t2 = Task.Run(() => NonBlockingProducer(numberCollection, cts.Token));

        // Wait for the tasks to complete execution
        Task.WaitAll(t1, t2);

        cts.Dispose();
        Console.WriteLine("Press the Enter key to exit.");
        Console.ReadLine();
    }

    static void NonBlockingConsumer(BlockingCollection<int> bc, CancellationToken ct)
    {
        while (!bc.IsCompleted)
        {
            int nextItem = 0;
            try
            {
                if (!bc.TryTake(out nextItem, 0, ct))
                {
                    Console.WriteLine(" Take Blocked");
                }
                else
                {
                    Console.WriteLine(" Take:{0}", nextItem);
                }
            }

            catch (OperationCanceledException)
            {
                Console.WriteLine("Taking canceled.");
                break;
            }

            // Slow down consumer just a little to cause
            // collection to fill up faster, and lead to "AddBlocked"
            Thread.SpinWait(500000);
        }

        Console.WriteLine("\r\nNo more items to take.");
    }

    static void NonBlockingProducer(BlockingCollection<int> bc, CancellationToken ct)
    {
        int itemToAdd = 0;
        bool success = false;

        do
        {
            // Cancellation causes OCE. We know how to handle it.
            try
            {
                // A shorter timeout causes more failures.
                success = bc.TryAdd(itemToAdd, 2, ct);
            }
            catch (OperationCanceledException)
            {
                Console.WriteLine("Add loop canceled.");
                // Let other threads know we're done in case
                // they aren't monitoring the cancellation token.
                bc.CompleteAdding();
                break;
            }

            if (success)
            {
                Console.WriteLine(" Add:{0}", itemToAdd);
                itemToAdd++;
            }
            else
            {
                Console.Write(" AddBlocked:{0} Count = {1}", itemToAdd.ToString(), bc.Count);
                // Don't increment nextItem. Try again on next iteration.

                //Do something else useful instead.
                UpdateProgress(itemToAdd);
            }

        } while (itemToAdd < inputs);

        // No lock required here because only one producer.
        bc.CompleteAdding();
    }

    static void UpdateProgress(int i)
    {
        double percent = ((double)i / inputs) * 100;
        Console.WriteLine("Percent complete: {0}", percent);
    }
}

```

## <a name="see-also"></a>Siehe auch

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)

[Übersicht über BlockingCollection](blockingcollection-overview.md)

