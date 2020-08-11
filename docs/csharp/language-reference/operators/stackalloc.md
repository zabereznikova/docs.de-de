---
title: stackalloc-Ausdruck – C#-Referenz
ms.date: 03/13/2020
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc expression [C#]
ms.openlocfilehash: 4f20f3262b77cc2fe16480e53d13960e68d230b5
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916673"
---
# <a name="stackalloc-expression-c-reference"></a>stackalloc-Ausdruck (C#-Referenz)

Ein `stackalloc`-Ausdruck ordnet einen Speicherblock im Stapel zu. Ein während der Ausführung der Methode im Stapel zugeordneter Speicherblock wird automatisch verworfen, wenn diese Methode zurückgegeben wird. Sie können den mit `stackalloc` zugeordneten Speicher nicht explizit freigeben. Ein im Stapel zugeordneter Speicherblock unterliegt nicht der [automatischen Speicherbereinigung](../../../standard/garbage-collection/index.md) und muss nicht mit einer [`fixed`-Anweisungen](../keywords/fixed-statement.md) angeheftet werden.

Sie können das Ergebnis eines `stackalloc`-Ausdrucks einer Variablen mit einem der folgenden Typen zuweisen:

- Ab C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> oder <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, wie im folgenden Beispiel gezeigt:

  [!code-csharp[stackalloc span](snippets/shared/StackallocOperator.cs#AssignToSpan)]

  Sie müssen keinen [unsicheren](../keywords/unsafe.md) Kontext verwenden, wenn Sie der Variablen <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601> einen im Stapel zugeordneten Speicherblock zuweisen.

  Wenn Sie mit diesen Typen arbeiten, können Sie einen `stackalloc`-Ausdruck in [bedingten](conditional-operator.md) oder Zuweisungsausdrücken verwenden, wie das folgende Beispiel zeigt:

  [!code-csharp[stackalloc expression](snippets/shared/StackallocOperator.cs#AsExpression)]

  Ab C# 8.0 können Sie einen `stackalloc`-Ausdruck innerhalb anderer Ausdrücke immer dann verwenden, wenn eine <xref:System.Span%601>- oder <xref:System.ReadOnlySpan%601>-Variable zulässig ist, wie im folgenden Beispiel zu sehen:

  [!code-csharp[stackalloc in nested expressions](snippets/shared/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > Wir empfehlen, die Typen <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601> zu verwenden, um nach Möglichkeit mit dem im Stapel zugeordneten Speicher zu arbeiten.

- Ein [Zeigertyp](../../programming-guide/unsafe-code-pointers/pointer-types.md), wie im folgenden Beispiel gezeigt:

  [!code-csharp[stackalloc pointer](snippets/shared/StackallocOperator.cs#AssignToPointer)]

  Wie das vorhergehende Beispiel zeigt, müssen Sie einen `unsafe`-Kontext verwenden, wenn Sie mit Zeigertypen arbeiten.

  Im Fall von Zeigertypen können Sie einen `stackalloc`-Ausdruck nur in einer lokalen Variablendeklaration zum Initialisieren der Variable verwenden.

Die Menge des verfügbaren Speichers im Stapel ist begrenzt. Wenn Sie zu viel Speicher im Stapel zuordnen, wird eine <xref:System.StackOverflowException> ausgelöst. Beachten Sie die folgenden Regeln, um dies zu vermeiden:

- Begrenzen Sie die Speichermenge, die Sie mit `stackalloc` zuordnen:

  [!code-csharp[limit stackalloc](snippets/shared/StackallocOperator.cs#LimitStackalloc)]

  Da die Menge des auf im Stapel verfügbaren Speichers von der Umgebung abhängt, in der der Code ausgeführt wird, sollten Sie bei der Festlegung des tatsächlichen Grenzwerts konservativ vorgehen.

- Vermeiden Sie die Verwendung von `stackalloc` in Schleifen. Ordnen Sie den Speicherblock außerhalb einer Schleife zu, und verwenden Sie ihn innerhalb der Schleife wieder.

Der Inhalt des neu zugeordneten Speichers ist undefiniert. Er sollte vor Verwendung initialisiert werden. Beispielsweise können Sie die <xref:System.Span%601.Clear%2A?displayProperty=nameWithType>-Methode verwenden, die alle Elemente auf den Standardwert des Typs `T` festlegt.

Ab C# 7.3 können Sie mit der Arrayinitialisierungssyntax den Inhalt des neu zugeordneten Speichers definieren. Das folgende Beispiel zeigt verschiedene Möglichkeiten, dies zu erreichen:

[!code-csharp[stackalloc initialization](snippets/shared/StackallocOperator.cs#StackallocInit)]

Im Ausdruck `stackalloc T[E]` muss `T` ein [nicht verwalteter Typ](../builtin-types/unmanaged-types.md) sein und `E` in einen nicht negativen [int](../builtin-types/integral-numeric-types.md)-Wert ausgewertet werden.

## <a name="security"></a>Sicherheit

Mit der Verwendung von `stackalloc` werden automatisch Funktionen zum Erkennen eines Pufferüberlaufs in der Common Language Runtime (CLR) aktiviert. Wenn ein Pufferüberlauf erkannt wird, wird der Vorgang so schnell wie möglich beendet, damit das Risiko der Ausführung von schädlichem Code verringert wird.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Stapelzuordnung](~/_csharplang/spec/unsafe-code.md#stack-allocation) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md) sowie im Vorschlag zum Feature [Zulassen von `stackalloc` in geschachtelten Kontexten](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
- [Operatoren im Zusammenhang mit Zeigern](pointer-related-operators.md)
- [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Memory- und Span-bezogene Typen](../../../standard/memory-and-spans/index.md)
- [Empfehlungen und Warnungen für „stackalloc“](https://vcsjones.dev/2020/02/24/stackalloc/)
