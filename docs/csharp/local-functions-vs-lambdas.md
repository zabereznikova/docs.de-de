---
title: "Lokale Funktionen im Vergleich zu Lambdaausdrücken"
description: "Erfahren Sie, warum lokale Funktionen unter Umständen besser geeignet sind als Lambdaausdrücke."
keywords: "C#, .NET, .NET Core, neueste Funktionen, Neuigkeiten, lokale Funktionen, Lambdaausdrücke"
author: BillWagner
ms.author: wiwagn
ms.date: 06/27/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.openlocfilehash: 20312b58a24dc991791edad4bb92d3a8ca6d501a
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2017
---
# <a name="local-functions-compared-to-lambda-expressions"></a>Lokale Funktionen, die im Vergleich zu Lambda-Ausdrücke

Auf den ersten Blick sind [lokale Funktionen](programming-guide/classes-and-structs/local-functions.md) und [Lambdaausdrücke](lambda-expressions.md) sehr ähnlich. In vielen Fällen ist die Wahl zwischen der Verwendung von Lambda-Ausdrücke und lokale Funktionen nur wenige der Stil und einem persönlichen Vorlieben. Es gibt jedoch real Unterschiede in den dort können Sie verwenden eine oder andere, die Sie kennen sollten.

Sehen wir uns die Unterschiede zwischen der Implementierungen des Fakultätsalgorithmus als lokale Funktion und als Lambdaausdruck an. Erste die Version mit einer lokalen Funktion:

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

Vergleichen Sie diese Implementierung mit einer Version, die Lambdaausdrücke verwendet:

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

Der lokalen Funktionen haben Namen. Der Lambda-Ausdrücke sind anonyme Methoden, die auf Variablen zugewiesen sind, sind `Func` oder `Action` Typen. Wenn Sie eine lokale Funktion deklarieren, gehören die Argumenttypen und der Rückgabetyp der Funktionsdeklaration. Statt Bestandteil der Text des Lambda-Ausdrucks gehören Ausdruck, der Argumenttypen und der Rückgabetyp des Lambda-Ausdrucks Variablentyp Deklaration. Diese zwei Unterschiede klarer Code zur Folge.

Lokale Funktionen besitzen verschiedene Regeln für die definitive Zuweisung als Lambda-Ausdrücke. Eine lokale Funktionsdeklaration kann von jedem Ort Code verwiesen werden, in denen sich im Bereich befindet. Ein Lambda-Ausdruck muss in einer zuweisungsanordnung zugewiesen werden, bevor Zugriff auf (oder möglich durch die Delgate verweisen auf den Lambda-Ausdruck aufgerufen.) Beachten Sie, dass die Version mit Lambdaausdrücken den Lambdaausdruck `nthFactorial` deklarieren und initialisieren muss, bevor er definiert wird. Wird das nicht gemacht, führt dies zu einem Kompilierzeitfehler, weil auf `nthFactorial` verwiesen wurde, bevor es zugewiesen wurde.
Das bedeutet, rekursive Algorithmen einfacher zu erstellen, mit der lokalen Funktionen sind. Sie können deklarieren und definieren eine lokale Funktion, die sich selbst aufruft. Lambda-Ausdrücke müssen deklariert werden und ein Standardwert zugewiesen werden, bevor sie einen Text neu zugewiesen werden können, die der gleichen Lambdaausdruck verweist auf.

Definitiven Zuweisungsregeln wirken sich auch auf alle Variablen, die von der lokalen Epression der Funktion oder Lambda-Ausdruck erfasst werden. Lokale Funktionen und Lambda-Ausdruck Regeln fordern, dass alle erfassten Variablen an dem Punkt definitiv zugewiesen werden, wenn der lokale-Funktion oder einen Lambda-Ausdruck in einen Delegaten konvertiert wird. Der Unterschied ist, dass Lambda-Ausdrücke in Delegaten konvertiert werden, wenn sie deklariert werden. Lokale Funktionen werden in Delegaten nur bei Verwendung als einen Delegaten konvertiert. Wenn Sie eine lokale zu deklarieren und darauf nur verweisen, indem Sie diese wie eine Methode aufruft, wird er nicht in einen Delegaten konvertiert werden. Diese Regel können Sie eine lokale Funktion an einen beliebigen Ort in seinem einschließenden Bereich zu deklarieren. Es ist üblich, deklarieren Sie lokale Funktionen am Ende der übergeordneten Methode nach return-Anweisungen.

Der Compiler kann im dritten statische Analysen durchführen, die lokale Funktionen erfasste Variablen im einschließenden Bereich definitiv zugewiesen ermöglicht. Betrachten Sie das folgende Beispiel:

```csharp
bool M()
{
    int y;
    Local();
    return y;

    void Local() => y = 0;
}
```

Der Compiler können Sie ermitteln, `Local` definitiv zugewiesen `y` beim Aufruf. Da `Local` wird aufgerufen, bevor die `return` -Anweisung `y` Definitiely wird zugewiesen werden, auf die `return` Anweisung.

Die Analyse, die es ermöglicht, dass die Analyse den vierten Unterschied ermöglicht.
Je nach ihrer Verwendung können lokale Funktionen Heapzuordnungen vermeiden, die immer für Lambda-Ausdrücke erforderlich sind. Wenn eine lokale Funktion niemals in einen Delegaten konvertiert wird und keines der Variablen, die von der lokalen Funktion erfasst, die von anderen Lambdas oder lokale Funktionen, die in Delegaten konvertiert werden aufgezeichnet wird, kann der Compiler Heapzuordnungen vermeiden. 

Betrachten Sie das folgende asynchrone Beispiel:

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

Der Abschluss dieses Lambdaausdrucks enthält die Variablen `address`, `index` und `name`. Im Fall von lokalen Funktionen ist das Objekt, das den Abschluss implementiert, möglicherweise vom Typ `struct`. Dieses Strukturtyps würde durch Verweis auf die lokale Funktion übergeben werden. Dieser Unterschied in der Implementierung würde auf eine Zuweisung zu speichern.

Die Instanziierung für Lambda-Ausdrücke erforderlich bedeutet, dass zusätzliche speicherbelegungen, u. u. einen Faktor in zeitkritischem Codepfaden.
Lokale Funktionen erfordern diesen Mehraufwand nicht. Im obigen Beispiel hat die Version mit der lokalen Funktion zwei Zuordnungen weniger als die Version mit dem Lambdaausdruck.

> [!NOTE]
> Die Entsprechung dieser Methode mit der lokalen Funktion verwendet auch eine Klasse für den Abschluss. Ob der Abschluss für eine lokale Funktion als `class` oder `struct` implementiert wird, ist ein Implementierungsdetail. Eine lokale Funktion verwendet möglicherweise `struct`, während ein Lambdaausdruck immer `class` nutzt.

[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]

Eine letzter Vorteil, der in diesem Beispiel zu kurz gekommen ist, besteht darin, dass lokale Funktionen mithilfe der `yield return`-Syntax als Iteratoren implementiert werden können, um eine Sequenz von Werten zu erzeugen. Die `yield return` Anweisung ist in Lambda-Ausdrücken nicht zulässig.

Während lokale Funktionen für Lambdaausdrücke als überflüssig erscheinen, dienen sie tatsächlich anderen Zwecken und haben unterschiedliche Verwendungen.
Lokale Funktionen sind effizienter, im Fall dass Sie eine Funktion schreiben möchten, die nur aus dem Kontext einer anderen Methode abgerufen wird.
