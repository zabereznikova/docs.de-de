---
title: Delegaten und Lambdas
description: Erfahren Sie, wie Delegaten, die einen Typ definieren, der eine bestimmte Methodensignatur angibt, direkt aufgerufen oder erst an eine andere Methode übergeben und dann aufgerufen werden können.
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: a9ca935814d1a7f77ded5f371ccd496c3859c523
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635927"
---
# <a name="delegates-and-lambdas"></a>Delegaten und Lambdas

Delegaten definieren einen Typ, der eine bestimmte Methodensignatur angibt. Eine Methode (statische Methode oder Instanzmethode), die dieser Signatur entspricht, kann einer Variablen dieses Typs zugewiesen werden. Anschließend kann sie (mit den entsprechenden Argumenten) direkt aufgerufen oder selbst als Argument an eine andere Methode übergeben und dann aufgerufen werden. Das folgende Beispiel veranschaulicht die Verwendung von Delegaten.

```csharp
using System;
using System.Linq;

public class Program
{
    public delegate string Reverse(string s);

    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Reverse rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

* In Zeile `public delegate string Reverse(string s);` wird ein Delegattyp mit einer bestimmten Signatur erstellt – in diesem Fall eine Methode, die einen Zeichenfolgenparameter akzeptiert und dann einen Zeichenfolgenparameter zurückgibt.
* Die Methode `static string ReverseString(string s)`, die über die gleiche Signatur wie der definierte Delegattyp verfügt, implementiert den Delegaten.
* Die Zeile `Reverse rev = ReverseString;` zeigt, dass Sie eine Methode einer Variable des entsprechenden Delegattyps zuweisen können.
* Die Zeile `Console.WriteLine(rev("a string"));` zeigt, wie eine Variable eines Delegattyps benutzt wird, um den Delegaten aufzurufen.

Um den Entwicklungsprozess zu optimieren, enthält .NET eine Reihe von Delegattypen, die Programmierer verwenden können, damit sie keine neuen Typen erstellen müssen. Diese Typen lauten `Func<>`, `Action<>` und `Predicate<>`. Sie können verwendet werden, ohne dass neue Delegattypen definiert werden müssen. Es gibt einige Unterschiede zwischen den drei Typen, und diese betreffen ihren jeweiligen Verwendungszweck:

* `Action<>` wird verwendet, wenn eine Aktion mithilfe der Argumente des Delegaten ausgeführt werden muss. Die von dem Typ gekapselte Methode gibt keinen Wert zurück.
* `Func<>` wird üblicherweise verwendet, wenn eine Transformation ausgeführt werden muss, Sie also die Argumente des Delegaten in ein anderes Ergebnis transformieren müssen. Projektionen sind ein gutes Beispiel. Die von dem Typ gekapselte Methode gibt einen angegebenen Wert zurück.
* `Predicate<>` wird verwendet, wenn Sie ermitteln müssen, ob das Argument die Bedingung des Delegaten erfüllt. Sie können auch die Schreibweise `Func<T, bool>` verwenden. In diesem Fall gibt die Methode einen booleschen Wert zurück.

Wir schreiben jetzt das obige Beispiel neu, indem wir den `Func<>`-Delegaten anstelle eines benutzerdefinierten Typs verwenden. Das Programm wird weiterhin genau gleich ausgeführt.

```csharp
using System;
using System.Linq;

public class Program
{
    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Func<string, string> rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

In diesem einfachen Beispiel erscheint es überflüssig, eine Methode außerhalb der `Main`-Methode zu definieren. In .NET Framework 2,0 wurde das Konzept der *anonymen Delegaten* eingeführt, mit denen Sie „Inline“-Delegaten erstellen können, ohne einen zusätzlichen Typ oder eine zusätzliche Methode angeben zu müssen.

Im folgenden Beispiel filtert ein anonymer Delegat eine Liste nach geraden Zahlen und gibt sie dann an die Konsole aus.

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(
          delegate (int no)
          {
              return (no % 2 == 0);
          }
        );

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

Wie Sie sehen, besteht der Haupttext des Delegaten einfach nur aus einer Reihe von Ausdrücken, wie bei jedem anderen Delegaten auch. Anstatt aber eine separate Definition zu erstellen, haben wir ihn _ad hoc_ in den Aufruf der Methode <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> eingeführt.

Selbst bei dieser Vorgehensweise bleibt immer noch zu viel Code übrig, den wir nicht benötigen. Hier kommen *Lambdaausdrücke* ins Spiel. Lambdaausdrücke (sogenannte Lambdas) wurden in C# 3.0 eingeführt und stellen einen der wichtigsten Bausteine von LINQ (Language Integrated Query) dar. Sie sind einfach eine praktischere Syntax für die Verwendung von Delegaten. Sie deklarieren eine Signatur und einen Methodentext, besitzen aber keine eigene formale Identität, sofern sie nicht einem Delegaten zugewiesen sind. Im Gegensatz zu Delegaten können sie direkt als linke Seite der Ereignisregistrierung oder in verschiedenen LINQ-Klauseln und -Methoden zugewiesen werden.

Da ein Lambdaausdruck einfach nur eine weitere Möglichkeit ist, einen Delegaten anzugeben, können wir das obige Beispiel neu schreiben und einen Lambdaausdruck anstelle eines anonymen Delegaten verwenden.

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(i => i % 2 == 0);

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

Im vorherigen Beispiel wird der Lambdaausdruck `i => i % 2 == 0` verwendet. Wie bereits erläutert, handelt es sich einfach um eine praktischere Syntax für die Verwendung von Delegaten. Die Ausführung des Codes erfolgt auf die gleiche Weise wie für anonyme Delegaten.

Noch einmal: Lambdas sind einfach Delegaten. Das bedeutet, dass sie problemlos als Ereignishandler verwendet werden können, wie im folgenden Codeausschnitt veranschaulicht.

```csharp
public MainWindow()
{
    InitializeComponent();

    Loaded += (o, e) =>
    {
        this.Title = "Loaded";
    };
}
```

Der `+=`-Operator in diesem Kontext wird zum Abonnieren eines [Ereignisses](../../docs/csharp/language-reference/keywords/event.md) verwendet. Weitere Informationen finden Sie unter [Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../docs/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="further-reading-and-resources"></a>Weitere Informationen und Ressourcen

* [Delegaten](../../docs/csharp/programming-guide/delegates/index.md)
* [Anonyme Funktionen](../../docs/csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
* [Lambda-Ausdrücke](../../docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
