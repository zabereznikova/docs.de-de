---
title: System.Delegate und das `delegate`-Schlüsselwort
description: Informationen zu den Klassen in .NET, die Delegaten unterstützen, und wie diese zum Schlüsselwort „delegate“ zugeordnet werden.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: f3742fda-13c2-4283-8966-9e21c2674393
ms.openlocfilehash: 87fdf19c4ea810c5ac4409fe16c3cba9d5fc6574
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146280"
---
# <a name="systemdelegate-and-the-delegate-keyword"></a>System.Delegate und das `delegate`-Schlüsselwort

[Zurück](delegates-overview.md)

Dieser Artikel enthält Informationen zu den Klassen in .NET, die Delegaten unterstützen, und wie diese dem Schlüsselwort `delegate` zugeordnet werden.

## <a name="define-delegate-types"></a>Definieren von Delegattypen

Wir beginnen mit dem Schlüsselwort „delegate“, da Sie dieses beim Arbeiten mit Delegaten hauptsächlich verwenden werden. Der Code, der vom Compiler bei Verwendung des `delegate`-Schlüsselworts generiert wird, verweist auf Methodenaufrufe, die Member der Klassen <xref:System.Delegate> und <xref:System.MulticastDelegate> aufrufen.

Sie definieren einen Delegattyp, der Syntax verwendet, die dem Definieren einer Methodensignatur ähnlich ist. Sie fügen das `delegate`-Schlüsselwort einfach der Definition hinzu.

Wir verwenden die List.Sort()-Methode weiterhin als Beispiel. Der erste Schritt ist die Erstellung eines Typs für den Vergleichsdelegaten:

```csharp
// From the .NET Core library

// Define the delegate type:
public delegate int Comparison<in T>(T left, T right);
```

Der Compiler generiert eine von `System.Delegate` abgeleitete Klasse, die der verwendeten Signatur entspricht (in diesem Fall eine Methode, die eine ganze Zahl zurückgibt und über zwei Argumente verfügt). Der Typ des Delegaten ist `Comparison`. Der Delegattyp `Comparison` ist ein generischer Typ. Weitere Informationen zu Generics finden Sie [hier](programming-guide/generics/index.md).

Beachten Sie, dass es so scheinen kann, als ob die Syntax eine Variable deklariert, aber tatsächlich deklariert sie einen *Typ*. Sie können Delegattypen innerhalb von Klassen, direkt in Namespaces oder sogar im globalen Namespace definieren.

> [!NOTE]
> Es wird nicht empfohlen, Delegattypen (oder andere Typen) direkt im globalen Namespace zu deklarieren.

Der Compiler generiert auch Handler zum Hinzufügen und Entfernen für diesen neuen Typ, damit Clients dieser Klasse Methoden der Aufrufliste einer Instanz hinzufügen und entfernen können. Der Compiler erzwingt, dass die Signatur der Methode, die hinzugefügt oder entfernt wird, der Signatur bei der Deklaration der Methode entspricht.

## <a name="declare-instances-of-delegates"></a>Deklarieren von Instanzen von Delegaten

Nach dem Definieren des Delegats können Sie eine Instanz dieses Typs erstellen.
Wie alle Variablen in C# können Sie Delegatinstanzen nicht direkt in einem Namespace oder im globalen Namespace deklarieren.

```csharp
// inside a class definition:

// Declare an instance of that type:
public Comparison<T> comparator;
```

Der Typ der Variable ist `Comparison<T>`, der zuvor definierte Delegattyp. Der Name der Variablen ist `comparator`.

 Dieser obenstehende Codeausschnitt hat eine Membervariable innerhalb einer Klasse deklariert. Sie können auch Delegatvariablen deklarieren, die lokale Variablen oder Argumente von Methoden sind.

## <a name="invoke-delegates"></a>Aufrufen von Delegaten

Sie rufen die Methoden in der Aufrufliste eines Delegaten auf, indem Sie diesen Delegaten aufrufen. In der `Sort()`-Methode ruft der Code die Vergleichsmethode an, um zu bestimmen, in welcher Reihenfolge er die Objekte anordnet:

```csharp
int result = comparator(left, right);
```

In der Zeile darüber *ruft* der Code die Methode auf, die an den Delegaten angefügt ist.
Sie behandeln die Variable als Methodenname und rufen sie mit der üblichen Syntax für Methodenaufrufe auf.

Diese Codezeile macht eine unsichere Annahme: Es gibt keine Garantie, dass dem Delegaten ein Ziel hinzugefügt wurde. Wenn keine Ziele angehängt wurden, löst die Zeile darüber eine `NullReferenceException` aus. Die Ausdrücke, die verwendet werden, um dieses Problem zu beheben, sind komplizierter als eine einfache NULL-Überprüfung und werden später in dieser [Reihe](delegates-patterns.md) behandelt.

## <a name="assign-add-and-remove-invocation-targets"></a>Zuweisen, Hinzufügen und Entfernen von Aufrufzielen

So werden Delegattypen definiert und Delegatinstanzen deklariert und aufgerufen.

Entwickler, die die `List.Sort()`-Methode verwenden möchten, müssen eine Methode definieren, deren Signatur der Definition des Delegattypen entspricht, und diese dem Delegaten zuweisen, der von der sort-Methode verwendet wird. Diese Zuordnung fügt die Methode der Aufrufliste des Delegatobjekts hinzu.

Nehmen wir an, Sie möchten eine Liste von Zeichenfolgen nach Länge sortieren. Die Vergleichsfunktion kann folgende sein:

```csharp
private static int CompareLength(string left, string right) =>
    left.Length.CompareTo(right.Length);
```

Die Methode wird als private Methode deklariert. Das ist in Ordnung. Möglicherweise möchten Sie nicht, dass diese Methode Teil der öffentlichen Schnittstelle ist. Sie kann dennoch als Vergleichsmethode verwendet werden, wenn sie an einen Delegaten angefügt wird. Der aufrufende Code wird diese Methode an die Zielliste des Delegatobjekts anfügen lassen und kann über diesen Delegaten darauf zugreifen.

Sie erstellen diese Beziehung durch Übergeben dieser Methode an die `List.Sort()`-Methode:

```csharp
phrases.Sort(CompareLength);
```

Beachten Sie, dass der Name der Methode ohne Klammern verwendet wird. Das Verwenden der Methode als Argument teilt dem Compiler mit, dass er den Methodenverweis in einen Verweis konvertieren soll, der als Delegataufrufziel verwendet werden kann, und diese Methode als Aufrufziel anfügen soll.

Sie könnten auch explizit eine Variable vom Typ `Comparison<string>` deklarieren und diese zuweisen:

```csharp
Comparison<string> comparer = CompareLength;
phrases.Sort(comparer);
```

Wenn es sich bei der als Delegatziel verwendeten Methode um eine kleine Methode handelt, wird gewöhnlich die [Lambdaausdruck](./programming-guide/statements-expressions-operators/lambda-expressions.md)-Syntax für die Durchführung der Zuweisung verwendet:

```csharp
Comparison<string> comparer = (left, right) => left.Length.CompareTo(right.Length);
phrases.Sort(comparer);
```

Die Verwendung von Lambdaausdrücken für Delegatziele wird in einem [späteren Abschnitt](delegates-patterns.md) ausführlicher behandelt.

Das Sort()-Beispiel fügt dem Delegaten typischerweise eine einzelne Zielmethode an. Allerdings unterstützen Delegatobjekte Aufruflisten mit mehreren Zielmethoden, die an ein Delegatobjekt angefügt sind.

## <a name="delegate-and-multicastdelegate-classes"></a>Delegatklassen und MulticastDelegate-Klassen

Die oben beschriebene Sprachunterstützung bietet die Funktionen und Unterstützung, die Sie in der Regel bei der Arbeit mit Delegaten benötigen. Diese Features beruhen auf zwei Klassen im .NET Core Framework: <xref:System.Delegate> und <xref:System.MulticastDelegate>.

Die `System.Delegate`-Klasse und ihre einzige direkte untergeordnete Klasse `System.MulticastDelegate` bieten die Framework-Unterstützung für das Erstellen von Delegaten, das Registrieren von Methoden als Delegatziele und das Aufrufen aller Methoden, die als Delegatziel registriert sind.

Interessanterweise sind die Klassen `System.Delegate` und `System.MulticastDelegate` selbst keine Delegattypen. Sie bieten die Grundlage für alle spezifischen Delegattypen. Derselbe Sprachentwurfsprozess verlangte, dass keine Klasse deklariert werden kann, die von `Delegate` oder `MulticastDelegate` abgeleitet wird. Die C#-Sprachregeln verbieten dies.

Stattdessen erstellt der C#-Compiler Instanzen einer von `MulticastDelegate` abgeleiteten Klasse, wenn Sie das C#-Schlüsselwort verwenden, um Delegattypen zu deklarieren.

Dieser Entwurf hat seinen Ursprung in der ersten Version von C# und .NET. Ein Ziel des Entwurfsteams war sicherzustellen, dass die Sprache bei der Verwendung von Delegaten Typsicherheit erzwingt. Dies bedeutete sicherzustellen, dass Delegaten mit dem richtigen Typ und der richtigen Anzahl von Argumenten aufgerufen werden. Zudem sollte jeder Rückgabetyp zur Kompilierzeit richtig angegeben werden. Delegaten waren Teil von .NET Version 1.0, die es vor Generics gab.

Die beste Möglichkeit, diese Typsicherheit zu erzwingen, bestand darin, dass der Compiler die konkreten Delegatklassen erstellt, die die verwendete Methodensignatur darstellten.

Obwohl Sie abgeleitete Klassen nicht direkt erstellen können, verwenden Sie die Methoden, die auf diesen Klassen definiert sind. Nun sehen wir uns die am häufigsten verwendeten Methoden an, die Sie beim Arbeiten mit Delegaten verwenden werden.

An erster Stelle müssen Sie beachten, dass jeder Delegat, mit dem Sie arbeiten, von `MulticastDelegate` abgeleitet ist. Ein Multicastdelegat bedeutet, dass mehr als ein Methodenziel beim Aufrufen über einen Delegaten aufgerufen werden kann. Der ursprüngliche Entwurf sah eine Unterscheidung vor zwischen Delegaten, bei denen nur eine Zielmethode angefügt und aufgerufen werden konnte, und Delegaten, bei denen mehrere Zielmethoden angefügt und aufgerufen werden konnten. Diese Unterscheidung erwies sich in der Praxis jedoch als weniger nützlich als ursprünglich gedacht. Die zwei verschiedenen Klassen wurden bereits erstellt und befinden sich seit der ersten Veröffentlichung im Framework.

Die Methoden, die Sie bei der Arbeit mit Delegaten am häufigsten verwenden, sind `Invoke()` und `BeginInvoke()` / `EndInvoke()`. `Invoke()` ruft alle Methoden auf, die an eine bestimmte Delegatinstanz angefügt wurden. Wie oben gezeigt, werden Delegaten in der Regel mit der Aufrufsyntax-Methode auf der Delegatvariablen aufgerufen. Wie Sie [später in dieser Reihe](delegates-patterns.md) sehen werden, gibt es Muster, die direkt mit diesen Methoden arbeiten.

Nun haben Sie die Sprachsyntax und die Klassen gesehen, die Delegaten unterstützen. Als Nächstes untersuchen wir, wie stark typisierte Delegaten verwendet, erstellt und aufgerufen werden.

[Nächste](delegates-strongly-typed.md)
