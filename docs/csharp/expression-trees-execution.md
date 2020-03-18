---
title: Ausführen von Ausdrucksbaumstrukturen
description: Informationen zum Ausführen von Ausdrucksbaumstrukturen, indem sie in Anweisungen einer ausführbaren Zwischensprache (IL) konvertiert werden.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 109e0ac5-2a9c-48b4-ac68-9b6219cdbccf
ms.openlocfilehash: 802a83f52f9c05a99c3f49f8f6511eff81ef3eaa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146020"
---
# <a name="executing-expression-trees"></a>Ausführen von Ausdrucksbaumstrukturen

[Vorheriges – Framework-Typen, die Ausdrucksbaumstrukturen unterstützen](expression-classes.md)

Eine *Ausdrucksbaumstruktur* ist eine Datenstruktur, die Code darstellt.
Es ist ein nicht kompilierter und ausführbarer Code. Wenn Sie den .NET-Code ausführen möchten, der durch eine Ausdrucksbaumstruktur dargestellt wird, müssen Sie ihn in ausführbare IL-Anweisungen konvertieren.

## <a name="lambda-expressions-to-functions"></a>Lambdaausdrücke zu Funktionen

Sie können jede LambdaExpression oder jeden Typ, der von LambdaExpression in eine ausführbare IL abgeleitet wurde, konvertieren. Andere Ausdruckstypen können nicht direkt in Code konvertiert werden. Diese Einschränkung wirkt sich kaum auf die Praxis aus. Lambdaausdrücke sind die einzigen Typen von Ausdrücken, die Sie ausführen möchten, indem Sie sie in eine ausführbare Zwischensprache (Intermediate Language, IL) konvertieren. (Denken Sie darüber nach, was es bedeuten würde, eine `ConstantExpression` direkt auszuführen. Würde es etwas Nützliches bedeuten?) Jede beliebige Ausdrucksbaumstruktur, die eine `LambdaExpression` ist, oder ein abgeleiteter Typ von `LambdaExpression`, kann in eine IL konvertiert werden.
Der Ausdruckstyp `Expression<TDelegate>` ist das einzige konkrete Beispiel in den .NET Core-Bibliotheken. Hiermit wird ein Ausdruck dargestellt, der jedem Delegattyp zugeordnet ist. Da dieser Typ einem Delegattyp zugeordnet ist, kann .NET den Ausdruck untersuchen, und die IL für einen entsprechenden Delegaten generieren, der der Signatur des Lambdaausdrucks entspricht.

In den meisten Fällen erstellt dies eine einfache Zuordnung zwischen einem Ausdruck und seinem entsprechenden Delegaten. Angenommen, eine Ausdrucksbaumstruktur, die durch `Expression<Func<int>>` dargestellt wird, wird in einen Delegaten des Typs `Func<int>` konvertiert. Für einen Lambdaausdruck mit beliebigem Rückgabetyp und Argumentliste besteht ein Delegattyp, der der Zieltyp für den ausführbaren Code ist, der von diesem Lambdaausdruck dargestellt wird.

Der `LambdaExpression`-Typ enthält `Compile`- und `CompileToMethod`-Member, die Sie verwenden würden, um eine Ausdrucksbaumstruktur in ausführbaren Code zu konvertieren. Die `Compile`-Methode erstellt einen Delegaten. Die `CompileToMethod`-Methode aktualisiert ein `MethodBuilder`-Objekt mit der IL, das die kompilierte Ausgabe der Ausdrucksbaumstruktur darstellt. Beachten Sie, dass `CompileToMethod` nur im Desktop-Framework verfügbar ist, nicht in .NET Core.

Optional können Sie auch einen `DebugInfoGenerator` angeben, der das Symbol „Debuginformationen“ für das generierte Delegatobjekt empfängt. Dies ermöglicht es Ihnen, die Ausdrucksbaumstruktur in ein Delegatobjekt zu konvertieren, und über vollständige Debuginformationen über die generierten Delegate zu verfügen.

Sie würden einen Ausdruck mithilfe des folgenden Code in einen Delegaten konvertieren:

```csharp
Expression<Func<int>> add = () => 1 + 2;
var func = add.Compile(); // Create Delegate
var answer = func(); // Invoke Delegate
Console.WriteLine(answer);
```

Beachten Sie, dass der Delegattyp auf den Ausdruckstyp basiert. Sie müssen den Rückgabetyp und die Argumentliste kennen, wenn Sie das Delegatobjekt mit strikter Typzuordnung verwenden möchten. Die `LambdaExpression.Compile()`-Methode gibt den `Delegate`-Typ zurück. Sie müssen es in den richtigen Delegattyp umwandeln, um Kompilierzeittools die Argumentliste oder den Rückgabetyp überprüfen zu lassen.

## <a name="execution-and-lifetimes"></a>Ausführung und Lebensdauer

Sie führen den Code durch Aufrufen des Delegaten aus, den Sie beim Aufrufen von `LambdaExpression.Compile()` erstellt haben. Dies sehen Sie oben, wo `add.Compile()` einen Delegaten zurückgibt. Rufen Sie diesen Delegaten durch Aufrufen von `func()` aus, der den Code ausführt.

Dieser Delegat stellt den Code in der Ausdrucksbaumstruktur dar. Sie können das Handle für diesen Delegaten beibehalten und es später aufrufen. Sie müssen die Ausdrucksbaumstruktur nicht jedes Mal kompilieren, wenn Sie den Code ausführen möchten, den sie darstellt. (Beachten Sie, dass Ausdrucksbaumstrukturen unveränderlich sind und dass das spätere Kompilieren der gleichen Ausdrucksbaumstruktur einen Delegaten erstellt, der den gleichen Code ausführt.)

Ich rate Ihnen davon ab, zu versuchen, mehr anspruchsvollere Zwischenspeicherungsmechanismen zu erstellen, um die Leistungsfähigkeit durch Vermeiden unnötiger Kompilieraufrufe zu erhöhen. Das Vergleichen von zwei beliebigen Ausdrucksbaumstrukturen um festzustellen, ob sie den gleichen Algorithmus darstellen, wird auch zum Ausführen sehr zeitaufwändig sein. Sie werden wahrscheinlich feststellen, dass die Rechenzeit, die Sie durch Vermeiden zusätzlicher Aufrufe von `LambdaExpression.Compile()` sichern, durch die Zeit für das Ausführen von Code, der zwei verschiedene Ausdrucksbaumstrukturen bestimmt, die zum gleichen ausführbaren Code führen, mehr als verbraucht sein wird.

## <a name="caveats"></a>Hinweise

Das Kompilieren eines Lambdaausdrucks in einen Delegaten und das Aufrufen dieses Delegaten, ist einer der einfachsten Vorgänge, die Sie mit einer Ausdrucksbaumstruktur ausführen können. Trotz dieses einfachen Vorgangs gibt es jedoch Hinweise, die Sie beachten müssen.

Lambdaausdrücke erstellen Closures über lokale Variablen, auf die im Ausdruck verwiesen wird. Sie müssen sicherstellen, dass alle Variablen, die Teil des Delegaten wären, am Speicherort verwendet werden können, wo Sie `Compile` aufrufen sowie beim Ausführen des resultierenden Delegats.

Im Allgemeinen stellt der Compiler sicher, dass dies der Fall ist. Wenn jedoch der Ausdruck auf eine Variable zugreift, die `IDisposable` implementiert, ist es möglich, dass der Code das Objekt löschen kann, während es weiterhin in der Ausdrucksbaumstruktur aufrechterhalten wird.

Angenommen, dieser Code funktioniert gut, da `int` nicht `IDisposable` implementiert:

```csharp
private static Func<int, int> CreateBoundFunc()
{
    var constant = 5; // constant is captured by the expression tree
    Expression<Func<int, int>> expression = (b) => constant + b;
    var rVal = expression.Compile();
    return rVal;
}
```

Der Delegat hat einen Verweis auf die lokale Variable `constant` erfasst.
Auf diese Variable wird später zugegriffen, wenn die von `CreateBoundFunc` zurückgegebene Funktion ausgeführt wird.

Jedoch sollten Sie diese (ausgedachte) Klasse beachten, die `IDisposable` implementiert:

```csharp
public class Resource : IDisposable
{
    private bool isDisposed = false;
    public int Argument
    {
        get
        {
            if (!isDisposed)
                return 5;
            else throw new ObjectDisposedException("Resource");
        }
    }

    public void Dispose()
    {
        isDisposed = true;
    }
}
```

Wenn Sie es in einem Ausdruck verwenden, wie unten dargestellt, erhalten Sie eine `ObjectDisposedException` beim Ausführen von Code, auf den die `Resource.Argument`-Eigenschaft verweist:

```csharp
private static Func<int, int> CreateBoundResource()
{
    using (var constant = new Resource()) // constant is captured by the expression tree
    {
        Expression<Func<int, int>> expression = (b) => constant.Argument + b;
        var rVal = expression.Compile();
        return rVal;
    }
}
```

Der Delegat, der von dieser Methode zurückgegeben wurde, wurde über das `constant`-Objekt geschlossen, das verworfen wurde. (Es wurde verworfen, da es in einer `using`-Anweisung deklariert wurde.)

Nun, wenn Sie den von dieser Methode zurückgegebenen Delegaten ausführen, müssen Sie eine `ObjectDisposedException` haben, die zum Zeitpunkt der Ausführung ausgelöst wird.

Es scheint sonderbar, einen Laufzeitfehler zu haben, der ein Kompilierzeitkonstrukt darstellt, aber das ist nun mal gang und gäbe, wenn wir mit Ausdrucksbaumstrukturen arbeiten.

Es gibt viele Permutationen dieses Problem, daher ist es schwierig, eine allgemeine Anleitung zu bieten, um dies zu vermeiden. Seien Sie mit dem Zugriff auf lokale Variablen beim Definieren von Ausdrücken vorsichtig. Dies gilt auch beim Zugreifen auf Status im aktuellen Objekt (dargestellt durch `this`), wenn Sie eine Ausdrucksbaumstruktur erstellen, die durch eine öffentliche API zurückgegeben werden kann.

Der Code in einem Ausdruck kann auf Methoden oder Eigenschaften in anderen Assemblys verweisen. Auf diese Assembly muss zugegriffen werden können, wenn der Ausdruck definiert ist, und wenn sie kompiliert wird und das resultierende Delegat aufgerufen wird. Sie werden einer `ReferencedAssemblyNotFoundException` in Fällen begegnen, in denen es nicht vorhanden ist.

## <a name="summary"></a>Zusammenfassung

Ausdrucksbaumstrukturen, die Lambdaausdrücke darstellen, können kompiliert werden, um einen Delegaten zu erstellen, den Sie ausführen können. Dies bietet einen Mechanismus, um den durch eine Ausdrucksbaumstruktur dargestellten Code auszuführen.

Die Ausdrucksbaumstruktur stellt den Code dar, der für jedes angegebene Konstrukt ausgeführt werden würde, das Sie erstellen. Solange die Umgebung, in der Sie den Code kompilieren und ausführen, der Umgebung entspricht, in der Sie den Ausdruck erstellen, funktioniert alles wie erwartet. Wenn dies nicht der Fall ist, sind die Fehler sehr berechenbar, und sie werden in den ersten Tests von Code mithilfe der Ausdrucksbaumstrukturen abgefangen werden.

[Weiter – Interpretieren von Ausdrücken](expression-trees-interpreting.md)
