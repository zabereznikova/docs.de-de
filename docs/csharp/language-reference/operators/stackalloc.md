---
title: 'stackalloc-Operator: C#-Referenz'
ms.custom: seodec18
ms.date: 06/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 3be4e827e75e4e26a34d9ed70423af5aa317e7fb
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025002"
---
# <a name="stackalloc-operator-c-reference"></a>stackalloc-Operator (C#-Referenz)

Der `stackalloc`-Operator ordnet einen Speicherblock im Stapel zu. Ein während der Ausführung der Methode im Stapel zugeordneter Speicherblock wird automatisch verworfen, wenn diese Methode zurückgegeben wird. Sie können den mit dem `stackalloc`-Operator zugeordneten Speicher nicht explizit freigeben. Ein im Stapel zugeordneter Speicherblock unterliegt nicht der [automatischen](../../../standard/garbage-collection/index.md) Speicherbereinigung und muss nicht mit den [`fixed`-Anweisungen](../keywords/fixed-statement.md) angeheftet werden.

Sie können das Ergebnis des `stackalloc`-Operators einer Variablen mit einem der folgenden Typen zuweisen:

- Ab C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> oder <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, wie im folgenden Beispiel gezeigt:

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  Sie müssen keinen [unsicheren](../keywords/unsafe.md) Kontext verwenden, wenn Sie der Variablen <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601> einen im Stapel zugeordneten Speicherblock zuweisen.

  Wenn Sie mit diesen Typen arbeiten, können Sie einen `stackalloc`-Ausdruck in [bedingten](conditional-operator.md) oder Zuweisungsausdrücken verwenden, wie das folgende Beispiel zeigt:

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  > [!NOTE]
  > Wir empfehlen, die Typen <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601> zu verwenden, um nach Möglichkeit mit dem im Stapel zugeordneten Speicher zu arbeiten.

- Ein [Zeigertyp](../../programming-guide/unsafe-code-pointers/pointer-types.md), wie im folgenden Beispiel gezeigt:

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  Wie das vorhergehende Beispiel zeigt, müssen Sie einen `unsafe`-Kontext verwenden, wenn Sie mit Zeigertypen arbeiten.

Der Inhalt des neu zugeordneten Speichers ist undefiniert. Ab C# 7.3 können Sie mit der Arrayinitialisierungssyntax den Inhalt des neu zugeordneten Speichers definieren. Das folgende Beispiel zeigt verschiedene Möglichkeiten, dies zu erreichen:

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

## <a name="security"></a>Sicherheit

Mit der Verwendung von `stackalloc` werden automatisch Funktionen zum Erkennen eines Pufferüberlaufs in der Common Language Runtime (CLR) aktiviert. Wenn ein Pufferüberlauf erkannt wird, wird der Vorgang so schnell wie möglich beendet, damit das Risiko der Ausführung von schädlichem Code verringert wird.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Stapelzuordnung](~/_csharplang/spec/unsafe-code.md#stack-allocation) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [Operatoren im Zusammenhang mit Zeigern](pointer-related-operators.md)
- [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Memory- und Span-bezogene Typen](../../../standard/memory-and-spans/index.md)
