---
title: 'Tupeltypen: C#-Referenz'
description: 'Enthält Informationen zu C#-Tupeln: Einfache Datenstrukturen, die Sie verwenden können, um lose zusammenhängende Datenelemente zu gruppieren.'
ms.date: 07/09/2020
helpviewer_keywords:
- value tuples [C#]
ms.openlocfilehash: d996c7afecba1b58bfd8337fa444fd71790dd482
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471771"
---
# <a name="tuple-types-c-reference"></a>Tupeltypen (C#-Referenz)

Das Feature *Tupel* ist in C# 7.0 und höher verfügbar und bietet eine überschaubare Syntax zum Gruppieren von mehreren Datenelementen in einer einfachen Datenstruktur. Im folgenden Beispiel wird veranschaulicht, wie Sie eine Tupelvariable deklarieren, initialisieren und dafür auf die zugehörigen Datenmember zugreifen können:

[!code-csharp-interactive[tuple intro](snippets/shared/ValueTuples.cs#Introduction)]

Wie im obigen Beispiel zu sehen ist, geben Sie zum Definieren eines Tupeltyps die Typen aller Datenmember und optional die [Feldnamen](#tuple-field-names) an. Sie können keine Methoden in einem Tupeltyp definieren, aber Sie können die von .NET bereitgestellten Methoden verwenden. Dies wird im folgenden Beispiel veranschaulicht:

[!code-csharp-interactive[tuple methods](snippets/shared/ValueTuples.cs#MethodOnTuples)]

Ab C# 7.3 unterstützen Tupeltypen die [Gleichheitsoperatoren](../operators/equality-operators.md) `==` und `!=`. Weitere Informationen finden Sie im Abschnitt [Tupelgleichheit](#tuple-equality).

Tupeltypen sind [Werttypen](value-types.md), und Tupelelemente sind öffentliche Felder. Bei Tupeln handelt es sich also um *veränderliche* Werttypen.

> [!NOTE]
> Für das Feature „Tupel“ werden der Typ <xref:System.ValueTuple?displayProperty=nameWithType> und die zugehörigen generischen Typen (z. B. <xref:System.ValueTuple%602?displayProperty=nameWithType>) benötigt. Sie sind in .NET Core sowie in .NET Framework 4.7 und höher verfügbar. Fügen Sie dem Projekt das NuGet-Paket [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) hinzu, wenn Sie Tupel in einem Projekt nutzen möchten, das auf .NET Framework 4.6.2 oder früher ausgerichtet ist.

Sie können Tupel mit einer beliebig großen Anzahl von Elementen definieren:

[!code-csharp-interactive[large tuple](snippets/shared/ValueTuples.cs#LargeTuple)]

## <a name="use-cases-of-tuples"></a>Anwendungsfälle von Tupeln

Einer der häufigsten Anwendungsfälle für Tupel ist die Verwendung als Methodenrückgabetyp. Anstatt [`out`-Methodenparameter](../keywords/out-parameter-modifier.md) zu definieren, können Sie also Methodenergebnisse in einem Tupelrückgabetyp gruppieren. Dies ist im folgenden Beispiel veranschaulicht:

[!code-csharp-interactive[multiple method outputs](snippets/shared/ValueTuples.cs#MultipleReturns)]

Wie Sie im obigen Beispiel sehen, können Sie direkt mit der zurückgegebenen Tupelinstanz arbeiten oder sie in separate Variablen [dekonstruieren](#tuple-assignment-and-deconstruction).

Sie können Tupeltypen auch anstelle von [anonymen Typen](../../programming-guide/classes-and-structs/anonymous-types.md) verwenden, z. B. in LINQ-Abfragen. Weitere Informationen finden Sie unter [Auswählen zwischen anonymen Typen und Tupeltypen](../../../standard/base-types/choosing-between-anonymous-and-tuple.md).

Normalerweise verwenden Sie Tupel, um lose zusammengehörende Datenelemente zu gruppieren. Dies ist normalerweise bei privaten und internen Hilfsmethoden hilfreich. Erwägen Sie bei Verwendung einer öffentlichen API, den Typ [Klasse](../keywords/class.md) oder [Struktur](struct.md) zu definieren.

## <a name="tuple-field-names"></a>Tupelfeldnamen

Sie können die Namen von Tupelfeldern entweder in einem Ausdruck für die Tupelinitialisierung oder in der Definition eines Tupeltyps explizit angeben. Dies wird im folgenden Beispiel veranschaulicht:

[!code-csharp-interactive[explicit field names](snippets/shared/ValueTuples.cs#ExplicitFieldNames)]

Ab C# 7.1 gilt Folgendes: Wenn Sie keinen Feldnamen angeben, wird er ggf. vom Namen der entsprechenden Variablen in einem Ausdruck für die Tupelinitialisierung abgeleitet (wie im folgenden Beispiel):

[!code-csharp-interactive[inferred field names](snippets/shared/ValueTuples.cs#InferFieldNames)]

Dies wird als Tupel-Projektionsinitialisierer bezeichnet. Der Name einer Variablen wird in den folgenden Fällen nicht auf einen Tupelfeldnamen projiziert:

- Der Kandidatenname ist ein Membername eines Tupeltyps, z. B. `Item3`, `ToString` oder `Rest`.
- Beim Namen des Kandidaten handelt es sich um das Duplikat des expliziten oder impliziten Feldnamens eines anderen Tupels.

In diesen Fällen geben Sie entweder explizit den Namen eines Felds an oder greifen über den Standardnamen auf ein Feld zu.

Die Standardnamen von Tupelfeldern lauten `Item1`, `Item2`, `Item3` usw. Den Standardnamen eines Felds können Sie immer verwenden. Dies gilt auch, wenn ein Feldname explizit angegeben oder abgeleitet wird (wie im folgenden Beispiel):

[!code-csharp-interactive[default field names](snippets/shared/ValueTuples.cs#DefaultFieldNames)]

Bei der [Tupelzuweisung](#tuple-assignment-and-deconstruction) und bei [Vergleichen der Tupelgleichheit](#tuple-equality) werden Feldnamen nicht berücksichtigt.

Zur Kompilierzeit ersetzt der Compiler die nicht dem Standard entsprechenden Felder durch die jeweiligen Standardnamen. Daher sind explizit angegebene oder abgeleitete Feldnamen zur Laufzeit nicht verfügbar.

## <a name="tuple-assignment-and-deconstruction"></a>Tupelzuweisung und -dekonstruktion

C# unterstützt die Zuweisung zwischen Tupeltypen, die die beiden folgenden Bedingungen erfüllen:

- Beide Tupeltypen haben die gleiche Anzahl von Elementen.
- Für jede Tupelposition ist der Typ des rechten Tupelelements mit dem Typ des entsprechenden linken Tupelelements identisch oder implizit konvertierbar.

Die Werte von Tupelelementen werden gemäß der Reihenfolge der Tupelelemente zugewiesen. Die Namen von Tupelfeldern werden ignoriert und nicht zugewiesen. Dies wird im folgenden Beispiel veranschaulicht:

[!code-csharp-interactive[tuple assignment](snippets/shared/ValueTuples.cs#Assignment)]

Sie können auch den Zuweisungsoperator `=` verwenden, um eine Tupelinstanz in separate Variablen zu *dekonstruieren* . Hierfür können Sie eine der folgenden Vorgehensweisen wählen:

- Explizites Deklarieren des Typs jeder Variablen in Klammern:

  [!code-csharp-interactive[specify types of variables](snippets/shared/ValueTuples.cs#DeconstructExplicit)]

- Verwenden des Schlüsselworts `var` außerhalb der Klammern, um implizit typisierte Variablen zu deklarieren und die Typen vom Compiler ableiten zu lassen:

  [!code-csharp-interactive[implicitly typed variables](snippets/shared/ValueTuples.cs#DeconstructVar)]

- Verwenden von vorhandenen Variablen:

  [!code-csharp-interactive[existing variables](snippets/shared/ValueTuples.cs#DeconstructExisting)]

Weitere Informationen zur Dekonstruktion von Tupeln und anderen Typen finden Sie unter [Dekonstruieren von Tupeln und anderen Typen](../../deconstruct.md).

## <a name="tuple-equality"></a>Tupelgleichheit

Ab C# 7.3 unterstützen Tupeltypen die Operatoren `==` und `!=`. Mit diesen Operatoren werden Member des linken Operanden gemäß der Reihenfolge der Tupelelemente mit den entsprechenden Membern des rechten Operanden verglichen.

[!code-csharp-interactive[tuple equality](snippets/shared/ValueTuples.cs#TupleEquality)]

Wie im obigen Beispiel zu sehen ist, werden Tupelfeldnamen bei Operationen mit `==` und `!=` nicht berücksichtigt.

Zwei Tupel sind vergleichbar, wenn die beiden folgenden Bedingungen erfüllt sind:

- Beide Tupel weisen die gleiche Anzahl von Elementen auf. `t1 != t2` wird beispielsweise nicht kompiliert, wenn `t1` und `t2` über eine unterschiedliche Anzahl von Elementen verfügen.
- Für jede Tupelposition können die entsprechenden Elemente der linken und rechten Tupeloperanden mit den Operatoren `==` und `!=` verglichen werden. `(1, (2, 3)) == ((1, 2), 3)` wird beispielsweise nicht kompiliert, weil `1` nicht mit `(1, 2)` vergleichbar ist.

Die Operatoren `==` und `!=` vergleichen Tupel per „Kurzschluss“. Dies bedeutet, dass eine Operation sofort angehalten wird, wenn ein Paar mit ungleichen Elementen erkannt oder das Ende von Tupeln erreicht wird. Bevor ein Vergleich durchgeführt wird, werden aber *alle* Tupelelemente ausgewertet. Dies wird im folgenden Beispiel veranschaulicht:

[!code-csharp-interactive[tuple element evaluation](snippets/shared/ValueTuples.cs#TupleEvaluationForEquality)]

## <a name="tuples-as-out-parameters"></a>Tupel als out-Parameter

Normalerweise gestalten Sie eine Methode, die [`out`-Parameter](../keywords/out-parameter-modifier.md) enthält, in eine Methode um, die ein Tupel zurückgibt. Es gibt aber auch Fälle, in denen ein `out`-Parameter einen Tupeltyp aufweisen kann. Im folgenden Beispiel wird veranschaulicht, wie Sie Tupel als `out`-Parameter verwenden:

[!code-csharp-interactive[tuple as out parameter](snippets/shared/ValueTuples.cs#TupleAsOutParameter)]

## <a name="tuples-vs-systemtuple"></a>Vergleich von Tupeln und `System.Tuple`

C#-Tupel, die auf <xref:System.ValueTuple?displayProperty=nameWithType>-Typen basieren, unterscheiden sich von Tupeln, die auf <xref:System.Tuple?displayProperty=nameWithType>-Typen basieren. Es gibt die folgenden Hauptunterschiede:

- Bei `ValueTuple`-Typen handelt es sich um [Werttypen](value-types.md). `Tuple`-Typen sind [Verweistypen](../keywords/reference-types.md).
- `ValueTuple`-Typen sind veränderlich. `Tuple`-Typen sind unveränderlich.
- Datenmember von `ValueTuple`-Typen sind Felder. Datenmember von `Tuple`-Typen sind Eigenschaften.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Hinweisen zu Featurevorschlägen:

- [Ableiten von Tupelnamen (Tupel-Projektionsinitialisierer)](~/_csharplang/proposals/csharp-7.1/infer-tuple-names.md)
- [Unterstützung für `==` und `!=` in Tupeltypen](~/_csharplang/proposals/csharp-7.3/tuple-equality.md)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Werttypen](value-types.md)
- [Auswählen zwischen anonymen Typen und Tupeltypen](../../../standard/base-types/choosing-between-anonymous-and-tuple.md)
- <xref:System.ValueTuple?displayProperty=nameWithType>
