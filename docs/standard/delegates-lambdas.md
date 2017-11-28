---
title: Delegaten und Lambdas
description: "Erfahren Sie, wie Delegate einen Typ definieren, der eine bestimmte Methodensignatur angibt, die direkt aufgerufen oder erst an eine andere Methode übergeben und dann aufgerufen werden kann."
keywords: .NET, .NET Core
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: d04a158db4f97a0e37f8a92149a3f237ee2e5434
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="delegates-and-lambdas"></a>Delegaten und Lambdas

Delegaten definieren einen Typ, der eine bestimmte Methodensignatur angibt. Eine Methode (statische Methode oder Instanzmethode), die dieser Signatur entspricht, kann einer Variablen dieses Typs zugewiesen werden. Anschließend kann sie (mit den entsprechenden Argumenten) direkt aufgerufen oder selbst als Argument an eine andere Methode übergeben und dann aufgerufen werden. Das folgende Beispiel veranschaulicht die Verwendung von Delegaten.

```csharp
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

*   In Zeile 4 erstellen wir einen Delegattyp mit einer bestimmten Signatur – in diesem Fall eine Methode, die einen Zeichenfolgenparameter akzeptiert und dann einen Zeichenfolgenparameter zurückgibt.
*   In Zeile 6 definieren wir die Implementierung des Delegaten, indem wir eine Methode bereitstellen, die exakt die gleiche Signatur aufweist.
*   In Zeile 13 wird die Methode einem Typ zugewiesen, der dem `Reverse`-Delegaten entspricht.
*   In Zeile 15 rufen wir schließlich den Delegaten auf, indem wir eine Zeichenfolge übergeben, die umgekehrt werden soll.

Um den Entwicklungsprozess zu optimieren, enthält .NET eine Reihe von Delegattypen, die Programmierer verwenden können, damit sie keine neuen Typen erstellen müssen. Dies sind `Func<>`, `Action<>` und `Predicate<>`. Sie können an verschiedenen Stellen in den .NET-APIs verwendet werden, ohne dass neue Delegattypen definiert werden müssen. Natürlich gibt es Unterschiede zwischen den drei Typen, wie Sie in ihren Signaturen erkennen können. Hierbei handelt es sich meist um Unterschiede in der Art und Weise der Verwendung dieser Typen:

*   `Action<>` wird verwendet, wenn eine Aktion mithilfe der Argumente des Delegaten ausgeführt werden muss.
*   `Func<>` wird üblicherweise verwendet, wenn eine Transformation ausgeführt werden muss, Sie also die Argumente des Delegaten in ein anderes Ergebnis transformieren müssen. Projektionen sind ein gutes Beispiel hierfür.
*   `Predicate<>` wird verwendet, wenn Sie ermitteln müssen, ob das Argument die Bedingung des Delegaten erfüllt. Der Typ kann auch als `Func<T, bool>` geschrieben werden.

Wir schreiben jetzt das obige Beispiel neu, indem wir den `Func<>`-Delegaten anstelle eines benutzerdefinierten Typs verwenden. Das Programm wird weiterhin genau gleich ausgeführt.

```csharp
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

In diesem einfachen Beispiel erscheint es überflüssig, eine Methode außerhalb der Main()-Methode zu definieren. Aus diesem Grund wurde in .NET Framework 2.0 das Konzept der **anonymen Delegaten** eingeführt. Damit können Sie „Inlinedelegaten“ erstellen, ohne einen weiteren Typ oder eine zusätzliche Methode angeben zu müssen. Sie fügen einfach die Definition des Delegaten inline dort ein, wo Sie sie benötigen.

Als Beispiel verwenden wir unseren anonymen Delegaten, um eine Liste mit gerade Zahlen herauszufiltern und diese Zahlen in der Konsole auszugeben.

```csharp
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
      delegate(int no)
      {
          return (no%2 == 0);
      }
    );

    foreach (var item in result)
    {
        Console.WriteLine(item);
    }
  }
}
```

Beachten Sie die markierten Zeilen. Wie Sie sehen, besteht der Haupttext des Delegaten einfach nur aus einer Reihe von Ausdrücken, wie bei jedem anderen Delegaten auch. Anstatt aber eine separate Definition zu erstellen, haben wir ihn _ad hoc_ in den Aufruf der `FindAll()`-Methode des `List<T>`-Typs eingeführt.

Selbst bei dieser Vorgehensweise bleibt immer noch zu viel Code übrig, den wir nicht benötigen. Hier kommen **Lambdaausdrücke** ins Spiel.

Lambdaausdrücke (sogenannte Lambdas) wurden zum ersten Mal in C# 3.0 eingeführt und stellen einen der wichtigsten Bausteine von LINQ dar (Language Integrated Query). Sie sind einfach eine praktischere Syntax für die Verwendung von Delegaten. Sie deklarieren eine Signatur und einen Methodentext, besitzen aber keine eigene formale Identität, sofern sie nicht einem Delegaten zugewiesen sind. Im Gegensatz zu Delegaten können sie direkt als linke Seite der Ereignisregistrierung oder in verschiedenen LINQ-Klauseln und -Methoden zugewiesen werden.

Da ein Lambdaausdruck einfach nur eine weitere Möglichkeit ist, einen Delegaten anzugeben, können wir das obige Beispiel neu schreiben und einen Lambdaausdruck anstelle eines anonymen Delegaten verwenden.

```csharp
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

In den markierten Zeilen sehen Sie, wie ein Lambdaausdruck aussieht. Das ist einfach eine **sehr** praktische Syntax für die Verwendung von Delegaten. Hinter den Kulissen passiert das Gleiche wie bei anonymen Delegaten.

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

## <a name="further-reading-and-resources"></a>Weitere Informationen und Ressourcen

*   [Delegaten](https://msdn.microsoft.com/library/ms173171.aspx)
*   [Anonyme Funktionen](https://msdn.microsoft.com/library/bb882516.aspx)
*   [Lambda-Ausdrücke](https://msdn.microsoft.com/library/bb397687.aspx)
