---
title: Schreiben von sicherem und effizientem C#-Code
description: Durch Verbesserungen, die kürzlich an C# vorgenommen wurden, können Sie nun überprüfbaren sicheren Code schreiben, dessen Leistung vorher nur mit unsicherem Code zu erzielen war.
ms.date: 10/23/2018
ms.technology: csharp-advanced-concepts
ms.custom: mvc
ms.openlocfilehash: d4a7916b80e15c7f00fa0a7da213ed0593e0959d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78239975"
---
# <a name="write-safe-and-efficient-c-code"></a>Schreiben von sicherem und effizientem C#-Code

Dank neuer C#-Features können Sie nun überprüfbaren sicheren Code schreiben, der eine höhere Leistung ermöglicht. Wenn Sie diese Techniken mit Bedacht einsetzen, sind weniger Szenarios mit unsicherem Code erforderlich. Mit den neuen Features können Verweise auf Werttypen als Methodenargumente und auf Rückgabewerte von Methoden leichter verwendet werden. Wenn diese Strategien sicher angewendet werden, müssen weniger Werttypen kopiert werden. Durch die Verwendung von Werttypen können Sie die Anzahl der Speicherbelegungen und Garbage Collection-Vorgänge minimieren.

In vielen Codebeispielen in diesem Artikel werden die neuen Features von C# 7.2 verwendet. Um diese nutzen zu können, müssen Sie Ihr Projekt für die Verwendung von C# 7.2 oder höher konfigurieren. Weitere Informationen zum Festlegen der Sprachversion finden Sie unter [Konfigurieren der Sprachversion](language-reference/configure-language-version.md).

In diesem Artikel stehen Vorgehensweisen für die effiziente Ressourcenverwaltung im Vordergrund. Ein Vorteil bei der Nutzung von Werttypen besteht darin, dass häufig eine Heapspeicherbelegung vermieden wird. Der Nachteil ist, dass sie als Wert kopiert werden. Dies macht es schwieriger, Algorithmen zu optimieren, die mit großen Datenmengen arbeiten. Neue Sprachfeatures in C# 7.2 stellen Mechanismen bereit, die Verweise auf Werttypen nutzen und sicheren sowie effizienten Code ermöglichen. Wenn Sie diese Features geschickt einsetzen, können Sie sowohl Speicherbelegungen als auch Kopiervorgänge minimieren. In diesem Artikel werden diese neuen Features untersucht.

Folgende Empfehlungen zur Ressourcenverwaltung werden behandelt:

- Deklarieren Sie einen [`readonly struct`](language-reference/keywords/readonly.md#readonly-struct-example)-Typ, um einen Typ als **unveränderlich** festzulegen. Dadurch muss der Compiler weniger Kopien erstellen, wenn [`in`](language-reference/keywords/in-parameter-modifier.md)-Parameter verwendet werden.
- Wenn ein Typ nicht so festgelegt werden kann, dass er nicht veränderbar ist, deklarieren Sie `struct`-Member als `readonly`, um anzuzeigen, dass der Member den Zustand nicht ändert.
- Verwenden Sie einen [`ref readonly`](language-reference/keywords/ref.md#reference-return-values)-Verweisrückgabewert, wenn der Rückgabewert ein `struct`-Typ und größer als <xref:System.IntPtr.Size?displayProperty=nameWithType> ist und die Speicherlebensdauer die der Methode überschreitet, die den Wert zurückgibt.
- Übergeben Sie aus Leistungsgründen einen `readonly struct`-Typ als `in`-Parameter, wenn die Größe des Typs <xref:System.IntPtr.Size?displayProperty=nameWithType> überschreitet.
- Übergeben Sie niemals einen `struct`-Member als einen `in`-Parameter, es sei denn, er ist mit dem `readonly`-Modifikator deklariert, oder die Methode ruft nur `readonly`-Member der Struktur auf. Ein Verstoß gegen diese Anleitung kann die Leistung negativ beeinflussen und zu einem unklaren Verhalten führen.
- Verwenden Sie einen [`ref struct`](language-reference/keywords/ref.md#ref-struct-types)- oder `readonly ref struct`-Typ wie <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601>, um mit Speicher als Bytesequenz zu arbeiten.

Durch diese Techniken müssen Sie im Hinblick auf **Verweise** und **Werte** zwei konkurrierende Ziele abwägen. Variablen, die [Verweistypen](programming-guide/types/index.md#reference-types) sind, enthalten einen Verweis auf den Speicherort. Variablen, die [Werttypen](programming-guide/types/index.md#value-types) sind, enthalten den tatsächlichen Wert. Diese Unterschiede sind für die Verwaltung von Speicherressourcen entscheidend. **Werttypen** werden üblicherweise kopiert, wenn sie einer Methode übergeben oder von dieser zurückgegeben werden. Bei diesem Verhalten wird der Wert von `this` kopiert, wenn Member eines Werttyps aufgerufen werden. Der Kopieraufwand steht im Zusammenhang mit der Größe des Typs. Für **Verweistypen** wird auf dem verwalteten Heap Speicher belegt. Für jedes neue Objekt ist eine erneute Speicherbelegung erforderlich. Anschließend muss für dieses der Speicher wieder freigegeben werden. Beide Vorgänge nehmen Zeit in Anspruch. Der Verweis wird kopiert, wenn ein Verweistyp als Argument einer Methode übergeben oder von dieser zurückgegeben wird.

In diesem Artikel wird im Folgenden beispielhaft eine Struktur für einen Punkt im dreidimensionalen Raum verwendet, um die Empfehlungen zu erläutern:

```csharp
public struct Point3D
{
    public double X;
    public double Y;
    public double Z;
}
```

In verschiedenen Beispielen werden unterschiedliche Implementierungen vorgestellt.

## <a name="declare-readonly-structs-for-immutable-value-types"></a>Deklarieren von schreibgeschützten Strukturen für unveränderliche Werttypen

Wenn Sie einen `struct`-Typ mit dem `readonly`-Modifizierer deklarieren, wird dem Compiler signalisiert, dass ein unveränderlicher Typ erstellt werden soll. Der Compiler erzwingt diese Entwurfsentscheidung mit den folgenden Regeln:

- Alle Feldmember müssen `readonly` sein.
- Alle Eigenschaften, also auch automatisch implementierte, müssen schreibgeschützt sein.

Mit diesen beiden Regeln wird sichergestellt, dass kein Member von `readonly struct` den Zustand dieser Struktur verändert. Der `struct`-Typ ist unveränderlich. Die `Point3D`-Struktur kann wie im folgenden Beispiel gezeigt als unveränderlich definiert werden:

```csharp
readonly public struct ReadonlyPoint3D
{
    public ReadonlyPoint3D(double x, double y, double z)
    {
        this.X = x;
        this.Y = y;
        this.Z = z;
    }

    public double X { get; }
    public double Y { get; }
    public double Z { get; }
}
```

Sie sollten sich immer dann an diese Empfehlung halten, wenn die Entwurfsabsicht darin besteht, einen unveränderlichen Werttyp zu erstellen. Ein weiterer Vorteil ergibt sich aus eventuellen Leistungsverbesserungen. Mit `readonly struct` bringen Sie Ihre Entwurfsabsicht deutlich zum Ausdruck.

## <a name="declare-readonly-members-when-a-struct-cant-be-immutable"></a>Deklarieren von schreibgeschützten Member, wenn eine Struktur nicht so festgelegt werden kann, dass sie nicht veränderbar ist

Wenn ein Strukturtyp in C# 8.0 und höher veränderbar ist, sollten Sie Member, die nicht verändert werden können, mit `readonly` deklarieren. Im Folgenden finden Sie beispielsweise eine veränderbare Variation der 3D-Punktstruktur:

```csharp
public struct Point3D
{
    public Point3D(double x, double y, double z)
    {
        _x = x;
        _y = y;
        _z = z;
    }

    private double _x;
    public double X
    {
        readonly get => _x;
        set => _x = value;
    }

    private double _y;
    public double Y
    {
        readonly get => _y;
        set => _y = value;
    }

    private double _z;
    public double Z
    {
        readonly get => _z;
        set => _z = value;
    }

    public readonly double Distance => Math.Sqrt(X * X + Y * Y + Z * Z);

    public readonly override string ToString() => $"{X}, {Y}, {Z}";
}
```

Das vorhergehende Beispiel zeigt viele der Stellen, an denen Sie den `readonly`-Modifizierer anwenden können: Methoden, Eigenschaften und Eigenschaftenaccessoren. Wenn Sie automatisch implementierte Eigenschaften verwenden, fügt der Compiler dem `get`-Zugriff den `readonly`-Modifizierer für Lese- und Schreibeigenschaften hinzu. Der Compiler fügt den `readonly`-Modifizierer zu den automatisch implementierten Eigenschaftendeklarationen für Eigenschaften mit nur einem `get`-Zugriff hinzu.

Das Hinzufügen des `readonly`-Modifizierers zu Membern, die den Zustand nicht verändern, bietet zwei damit verbundene Vorteile: Der erste Vorteil ist, dass Sie mithilfe des Compilers die Umsetzung Ihrer Absicht erzwingen können. Dieser Member kann weder den Zustand der Struktur verändern, noch kann er auf ein Member zugreifen, der nicht ebenfalls mit `readonly` markiert ist. Der zweite Vorteil ist, dass der Compiler beim Zugriff auf einen `readonly`-Member keine defensiven Kopien von `in`-Parametern erstellt. Der Compiler kann diese Optimierung sicher durchführen, da er garantiert, dass der `struct`-Member nicht von einem `readonly`-Member verändert wird.

## <a name="use-ref-readonly-return-statements-for-large-structures-when-possible"></a>Verwenden von `ref readonly return`-Anweisungen für große Strukturen (wo möglich)

Sie können Werte als Verweis zurückgeben, wenn diese in der Rückgabemethode nicht lokal verwendet werden. Bei dieser Vorgehensweise wird nur der Verweis und nicht die Struktur kopiert. Im folgenden Beispiel kann für die `Origin`-Eigenschaft kein `ref`-Verweisrückgabewert verwendet werden, da der Rückgabewert eine lokale Variable ist:

```csharp
public Point3D Origin => new Point3D(0,0,0);
```

Die folgende Eigenschaftendefinition kann hingegen durchaus als Verweis zurückgegeben werden, weil der Rückgabewert ein statischer Member ist:

```csharp
public struct Point3D
{
    private static Point3D origin = new Point3D(0,0,0);

    // Dangerous! returning a mutable reference to internal storage
    public ref Point3D Origin => ref origin;

    // other members removed for space
}
```

Damit aufrufende Funktionen nicht den Ursprung verändern, sollten Sie den Wert als `ref readonly` zurückgeben:

```csharp
public struct Point3D
{
    private static Point3D origin = new Point3D(0,0,0);

    public static ref readonly Point3D Origin => ref origin;

    // other members removed for space
}
```

Durch die Rückgabe von `ref readonly` vermeiden Sie, dass größere Strukturen kopiert werden. Zusätzlich wird die Unveränderlichkeit interner Datenmember beibehalten.

An der Aufrufstelle können die aufrufenden Funktionen die `Origin`-Eigenschaft entweder als `ref readonly` oder als Wert verwenden:

[!code-csharp[AssignRefReadonly](../../samples/snippets/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

Die erste Zuweisung im vorhergehenden Code erstellt eine Kopie der Konstanten `Origin` und weist diese Kopie zu. Die zweite weist einen Verweis zu. Beachten Sie, dass der Modifizierer `readonly` Teil der Variablendeklaration sein muss. Der referenzierte Verweis kann nicht geändert werden. Derartige Versuche führen zu einem Kompilierzeitfehler.

Der `readonly`-Modifizierer ist für die Deklaration von `originReference` erforderlich.

Der Compiler erzwingt, dass die aufrufende Funktion den Verweis nicht ändern kann. Versuche einer direkten Wertzuweisung führen zu einem Kompilierzeitfehler. Der Compiler kann jedoch nicht wissen, ob eine Membermethode den Zustand der Struktur ändert.
Um sicherzustellen, dass das Objekt nicht geändert wird, erstellt der Compiler eine Kopie und ruft Memberverweise mit dieser auf. Alle Änderungen werden an der Defensivkopie vorgenommen.

## <a name="apply-the-in-modifier-to-readonly-struct-parameters-larger-than-systemintptrsize"></a>Anwenden des `in`-Modifizierer auf einen `readonly struct`-Parameter, der größer als `System.IntPtr.Size` ist

Das `in`-Schlüsselwort ergänzt die vorhandenen Schlüsselwörter `ref` und `out` zum Übergeben von Argumenten als Verweis. Durch das `in`-Schlüsselwort wird festgelegt, dass das Argument als Verweis übergeben wird, die aufgerufene Methode aber nicht den Wert ändert.

Dieser Zusatz bietet zahlreiche Möglichkeiten, Ihre Entwurfsabsicht auszudrücken.
Werttypen werden bei der Übergabe an eine aufgerufene Methode kopiert, wenn Sie keinen der folgenden Modifizierer in den Methodensignaturen angeben. Jeder dieser Modifizierer legt fest, dass eine Variable als Verweis übergeben wird, wodurch ein Kopieren vermieden wird. Jeder Modifizierer drückt eine andere Absicht aus:

- `out`: Diese Methode legt den Wert des Arguments fest, das als dieser Parameter verwendet wird.
- `ref`: Diese Methode kann den Wert des Arguments festlegen, das als dieser Parameter verwendet wird.
- `in`: Diese Methode ändert den Wert des Arguments nicht, das als dieser Parameter verwendet wird.

Wenn Sie den Modifizierer `in` zur Übergabe eines Arguments als Verweis hinzufügen, legen Sie als Entwurfsabsicht fest, dass Argumente als Verweis übergeben werden sollen, um unnötiges Kopieren zu vermeiden. Das als Argument verwendete Objekt soll nicht geändert werden.

Diese Vorgehensweise führt oft zu Leistungsverbesserungen für schreibgeschützte Werttypen, die größer als <xref:System.IntPtr.Size?displayProperty=nameWithType> sind. Bei einfachen Typen (`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` und `bool` sowie `enum`) fallen potenzielle Leistungssteigerungen hingegen minimal aus. Wenn für Typen, die kleiner als <xref:System.IntPtr.Size?displayProperty=nameWithType> sind, Werte als Verweis übergeben werden, kann dies sogar zu Leistungseinbußen führen.

Der folgende Code zeigt als Beispiel eine Methode, die den Abstand zwischen Punkten in einem 3D-Raum berechnet.

[!code-csharp[InArgument](../../samples/snippets/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#InArgument "Specifying an in argument")]

Die Argumente sind zwei Strukturen, die jeweils drei double-Werte enthalten. Ein double-Wert ist 8 Byte groß, also umfasst jedes Argument 24 Byte. Durch Angabe des Modifizierers `in` übergeben Sie abhängig von der Architektur des Computers einen 4-Byte- oder 8-Byte-Verweis an diese Argumente. Der Größenunterschied ist zwar gering, doch er summiert sich, wenn Ihre Anwendung diese Methode in einer kurzen Schleife mit vielen unterschiedlichen Werten aufruft.

Der Modifizierer `in` ergänzt `out` und `ref` auch in anderer Weise. Sie können keine überladenen Methoden erstellen, die sich nur durch das Vorhandensein von `in`, `out` oder `ref` unterscheiden. Diese neuen Regeln erweitern dasselbe Verhalten, das stets für `out`- und `ref`-Parameter definiert wurde. Für Werttypen kann ebenso wie für die Modifizierer `out` und `ref` kein Boxing durchgeführt werden, da der `in`-Modifizierer angewendet wird.

Der Modifizierer `in` kann auf einen beliebigen Member angewendet werden, der Parameter akzeptiert: Methoden, Delegaten, Lambdas, lokale Funktionen, Indexer, Operatoren.

Von `in`-Parametern wird ein weiteres Feature bereitgestellt, durch das Sie Literalwerte oder Konstanten als Argument für einen `in`-Parameter verwenden können. Außerdem müssen Sie im Gegensatz zu einem `ref`- oder `out`-Parameter den Modifizierer `in` nicht an der Aufrufsite anwenden. Der folgende Code zeigt zwei Beispiele zum Aufruf der `CalculateDistance`-Methode. Im ersten Beispiel werden zwei lokale Variablen als Verweis übergeben. Im zweiten Beispiel wird als Teil des Methodenaufrufs eine temporäre Variable erstellt.

[!code-csharp[UseInArgument](../../samples/snippets/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#UseInArgument "Specifying an In argument")]

Der Compiler kann auf verschiedene Weise den Schreibschutz eines `in`-Arguments erzwingen.  Zunächst kann die aufgerufene Methode nicht direkt einem `in`-Parameter zugewiesen werden. Eine direkte Zuweisung zu einem Feld eines `in`-Parameters ist nicht möglich, wenn dieser Wert vom Typ `struct` ist. Außerdem können Sie keinen `in`-Parameter an eine Methode übergeben, die den Modifizierer `ref` oder `out` verwendet.
Diese Regeln gelten für jedes Feld eines `in`-Parameters, falls das Feld vom Typ `struct` und auch der Parameter vom Typ `struct` ist. Tatsächlich gelten diese Regeln für mehrere Memberzugriffsebenen, falls die Typen auf allen Ebenen `structs` sind.
Der Compiler erzwingt, dass `struct`-Typen als `in`-Argumente übergeben werden und deren `struct`-Member schreibgeschützte Variablen sind, wenn sie als Argumente an anderen Methoden übergeben werden.

Durch die Verwendung von `in`-Parametern können potenzielle Leistungseinbußen vermieden werden, die durch Kopiervorgänge entstehen. Die Semantik eines Methodenaufrufs ändert sich hierdurch nicht. Aus diesem Grund müssen Sie nicht den `in`-Modifizierer an der Aufrufstelle angeben. Wenn Sie den `in`-Modifizierer an der Aufrufstelle weglassen, wird dem Compiler mitgeteilt, dass es aus folgenden Gründen zulässig ist, eine Kopie des Arguments zu erstellen:

- Ein Argumenttyp wird implizit in einen Parametertyp konvertiert; eine Identitätskonvertierung findet jedoch nicht statt.
- Das Argument ist ein Ausdruck, verfügt jedoch nicht über eine bekannte Speichervariable.
- Eine überladene Methode unterscheidet sich nur durch die (fehlende) Angabe von `in`. In diesem Fall wird die überladene Methode verwendet, für die Argumente als Wert übergeben werden.

Diese Regeln sind nützlich, wenn Sie vorhandenen Code anpassen und schreibgeschützte Verweisargumente verwenden. In der aufgerufenen Methode können Sie alle Instanzmethoden aufrufen, die als Wert übergebene Parameter verwendet. In diesen Instanzen wird eine Kopie des `in`-Parameters erstellt. Da der Compiler eine temporäre Variable für jeden `in`-Parameter erstellen kann, können Sie auch Standardwerte für jeden `in`-Parameter angeben. Im folgenden Codebeispiel wird der Ursprung (Punkt 0,0) als Standardwert für den zweiten Punkt verwendet:

[!code-csharp[InArgumentDefault](../../samples/snippets/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

Wenn der Compiler dazu gezwungen werden soll, schreibgeschützte Argumente als Verweis zu übergeben, müssen Sie wie im folgenden Beispiel gezeigt den `in`-Modifizierer für Argumente an der Aufrufstelle angeben:

[!code-csharp[UseInArgument](../../samples/snippets/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#ExplicitInArgument "Specifying an In argument")]

Durch dieses Verhalten können `in`-Parameter leichter über einen gewissen Zeitraum in große Codebasen, in denen Leistungssteigerungen möglich sind, eingeführt werden. Zuerst fügen Sie den `in`-Modifizierer den Methodensignaturen hinzu. Anschließend ergänzen Sie die Aufrufstellen um den `in`-Modifizierer und erstellen `readonly struct`-Typen, damit der Compiler keine defensive Kopien von `in`-Parametern an mehreren Speicherorten erstellt.

Der Parameter `in` kann auch mit Verweistypen oder numerischen Werten verwendet werden. Allerdings sind die Vorteile in beiden Fällen – wenn überhaupt – nur minimal.

## <a name="never-use-mutable-structs-as-in-in-argument"></a>Vermeiden von veränderlichen Strukturen als `in`-Argumente

In den bisher beschriebenen Strategien wurde erläutert, wie sich Kopien durch die Rückgabe von Verweisen und die Übergabe von Werten als Verweis vermeiden lassen. Diese Vorgehensweisen sind ideal für Argumenttypen, die mit `readonly struct` deklariert werden. Wenn dies nicht der Fall ist, muss der Compiler in vielen Situationen **defensive Kopien** erstellen, um den Schreibschutz von Argumenten zu erzwingen. Betrachten Sie das folgende Beispiel, in dem im dreidimensionalen Raum der Abstand eines Punkts vom Ursprung berechnet wird:

[!code-csharp[InArgument](../../samples/snippets/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#InArgument "Specifying an in argument")]

Die `Point3D`-Struktur ist *keine* schreibgeschützte Struktur. Im Methodenkörper werden sechs Aufrufe zum Zugriff auf die Eigenschaften ausgeführt. Diese Zugriffe erscheinen möglicherweise auf den ersten Blick sicher. Die `get`-Zugriffsmethode sollte schließlich nicht den Zustand eines Objekts ändern. Dies wird jedoch von keiner Programmiersprachregel erzwungen. Es handelt sich nur um eine Konvention. Jeder Typ könnte eine `get`-Zugriffsmethode implementieren, die den internen Zustand ändert. Ohne eine Garantie der Programmiersprache muss der Compiler eine temporäre Kopie des Arguments erstellen, bevor er einen Member aufruft. Der temporäre Speicher wird auf dem Stapel erstellt, die Werte des Arguments werden in den temporären Speicher kopiert, und der Wert wird bei jedem Memberzugriff als `this`-Argument in den Stapel kopiert. In vielen Situationen beeinträchtigen die Kopien die Leistung so, dass die Übergabe als Wert schneller als die Übergabe als schreibgeschützter Verweis ist, wenn der Argumenttyp nicht `readonly struct` ist.

Wenn stattdessen zur Abstandsberechnung die unveränderliche Struktur `ReadonlyPoint3D` verwendet wird, werden temporäre Objekte nicht benötigt:

[!code-csharp[readonlyInArgument](../../samples/snippets/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#ReadOnlyInArgument "Specifying a readonly in argument")]

Der Compiler generiert effizienteren Code, wenn Member vom Typ `readonly struct` aufgerufen werden: Im Gegensatz zur Kopie des Empfängers ist der `this`-Verweis immer ein `in`-Parameter, der als Verweis der Membermethode übergeben wird. Durch diese Optimierung werden Kopien vermieden, wenn Sie `readonly struct` als `in`-Argument verwenden.

Übergeben Sie keinen Nullwerte zulassenden Typ als ein `in`-Argument. Der Typ <xref:System.Nullable%601> ist nicht als schreibgeschützte Struktur deklariert. Dies bedeutet, dass der Compiler defensive Kopien für jedes Nullwerte zulassende Typargument generieren muss, das einer Methode mit dem `in`-Modifizierer in der Parameterdeklaration übergeben wird.

Im [Beispielrepository](https://github.com/dotnet/samples/tree/master/csharp/safe-efficient-code/benchmark) auf GitHub finden Sie ein Beispielprogramm, das die Leistungsunterschiede mithilfe von [BenchmarkDotNet](https://www.nuget.org/packages/BenchmarkDotNet/) veranschaulicht. Dabei wird die Übergabe einer veränderlichen Struktur als Wert und Verweis mit der Übergabe einer unveränderlichen Struktur als Wert und Verweis verglichen. Am schnellsten ist die Übergabe einer unveränderlichen Struktur als Verweis.

## <a name="use-ref-struct-types-to-work-with-blocks-or-memory-on-a-single-stack-frame"></a>Verwenden von `ref struct`-Typen als Speicherblöcke für einzelne Stapelrahmen

Ein zugehöriges Sprachfeature ist die Möglichkeit, einen Werttyp zu deklarieren, der auf einen einzelnen Stapelrahmen beschränkt ist. Durch die Einschränkung kann der Compiler mehrere Optimierungen vornehmen. Der primäre Beweggrund für dieses Feature waren <xref:System.Span%601> und zugehörige Strukturen. Wenn Sie die neuen und aktualisierten .NET-APIs verwenden, in denen der <xref:System.Span%601>-Typ verwendet wird, werden Sie Leistungsverbesserungen erzielen, die diese Optimierungen mit sich bringen.

Möglicherweise haben Sie ähnliche Anforderungen, wenn Sie mit Speicher arbeiten, der mit [`stackalloc`](language-reference/operators/stackalloc.md) erstellt wurde, oder wenn Sie Speicher aus Interop-APIs verwenden. Sie können für diese Anforderungen eigene `ref struct`-Typen definieren.

## <a name="readonly-ref-struct-type"></a>`readonly ref struct`-Typ

Das Deklarieren einer Struktur als `readonly ref` vereint die Vorteile und Einschränkungen der `ref struct`- und `readonly struct`-Deklarationen. Der von der schreibgeschützten Span-Struktur verwendete Speicher ist auf einen einzelnen Stapelrahmen beschränkt und kann nicht geändert werden.

## <a name="conclusions"></a>Zusammenfassung

Durch das Verwenden von Werttypen wird die Anzahl der Speicherbelegungen minimiert:

- Speicher für Werttypen wird für lokale Variablen und Methodenargumente auf dem Stapel belegt.
- Speicher für Werttypen, die Member von anderen Objekten sind, wird als Teil dieses Objekts belegt. Eine separate Speicherbelegung findet nicht statt.
- Speicher für Rückgabewerte des Werttyps wird auf dem Stapel belegt.

Für Verweistypen ist in denselben Situationen ein anderes Verhalten zu beobachten:

- Speicher für Verweistypen wird für lokale Variablen und Argumente auf dem Heap belegt. Der Verweis wird auf dem Stapel gespeichert.
- Speicher für Werttypen, die Member von anderen Objekten sind, wird separat belegt. Das enthaltende Objekt speichert den Verweis.
- Speicher für Rückgabewerte des Verweistyps wird auf dem Heap belegt. Der Verweis auf den Speicher wird auf dem Stapel gespeichert.

Das Minimieren von Speicherbelegungen hat auch Nachteile. Wenn die Größe des `struct`-Typs die des Verweises übersteigt, wird mehr Speicher kopiert. Ein Verweis ist in der Regel 64 Bit oder 32 Bit lang und von der CPU des Zielcomputers abhängig.

Diese Nachteile wirken sich in der Regel nur minimal auf die Leistung aus. Bei größeren Strukturen oder Sammlungen können jedoch höhere Leistungseinbußen auftreten. In Programmen können die Auswirkungen bei kurzen Schleifen und langsamen Pfaden gravierend sein.

Diese Erweiterungen von C# wurden für leistungskritische Algorithmen entwickelt, bei denen die Minimierung von Speicherbelegungen entscheidend ist, um die erforderliche Leistung zu erzielen. Sie werden feststellen, dass Sie diese Features möglicherweise nicht oft in dem Code verwenden, den Sie schreiben. Die Verbesserungen wurden jedoch global in .NET umgesetzt. Da immer mehr APIs diese Features nutzen, werden Sie feststellen, dass sich die Leistung Ihrer Anwendungen verbessert.

## <a name="see-also"></a>Siehe auch

- [ref (C#-Referenz)](language-reference/keywords/ref.md)
- [Ref-Rückgabetypen und lokale ref-Variablen](programming-guide/classes-and-structs/ref-returns.md)
