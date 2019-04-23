---
title: stackalloc-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 04/12/2018
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: 61a27e777a1919a2a6fc5140a311835a8f3daba9
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2019
ms.locfileid: "59480806"
---
# <a name="stackalloc-c-reference"></a>stackalloc (C#-Referenz)

Das Schlüsselwort `stackalloc` wird verwendet, um dem Stapel einen Speicherblock zuzuweisen.

```csharp
Span<int> block = stackalloc int[100];
```

Zuweisen der belegten Blöcke zu einem <xref:System.Span%601?displayName=nameWithType> anstelle von `int*` ermöglicht Stapelreservierungen in einem sicheren Block. Der `unsafe`-Kontext ist nicht erforderlich.

## <a name="remarks"></a>Anmerkungen

Das Schlüsselwort ist nur in lokalen Variableninitialisierern gültig. Folgender Code verursacht Compilerfehler.

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
Span<int> span;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
span = stackalloc int[100];
```

Ab C# 7.3 können Sie die Syntax des Arrayinitialisierers für `stackalloc`-Arrays verwenden. Alle nachfolgenden Deklarationen deklarieren ein Array mit drei Elementen, dessen Werte die ganzen Zahlen `1`, `2` und `3` darstellen. Die zweite Initialisierung weist den Speicher einem <xref:System.ReadOnlySpan%601> zu, damit angebend, dass der Arbeitsspeicher nicht geändert werden kann.

```csharp
// Valid starting with C# 7.3
Span<int> first = stackalloc int[3] { 1, 2, 3 };
ReadOnlySpan<int> second = stackalloc int[] { 1, 2, 3 };
Span<int> third = stackalloc[] { 1, 2, 3 };
```

Wenn Zeigertypen beteiligt sind, benötigt `stackalloc` einen [unsafe](unsafe.md)-Kontext. Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md).

`stackalloc` befindet sich wie [_alloca](/cpp/c-runtime-library/reference/alloca) in der C-Laufzeitbibliothek.

## <a name="examples"></a>Beispiele

Im folgenden Beispiel werden die ersten 20 Zahlen der Fibonacci-Folge berechnet und angezeigt. Jede Zahl bildet die Summe der beiden vorherigen Zahlen. Im Code wird dem Stapel, nicht dem Heap, ein Speicherblock zugewiesen, der groß genug ist, um 20 Elemente vom Typ `int` zu enthalten. Die Adresse des Blocks wird in `Span` `fib` gespeichert. Dieser Speicher unterliegt nicht der automatischen Speicherbereinigung und muss daher nicht (mithilfe von [fixed](fixed-statement.md)) angeheftet werden. Die Lebensdauer des Speicherblocks ist auf die Lebensdauer der definierenden Methode begrenzt. Sie können den Speicher nicht freigeben, bevor die Methode zurückgibt.

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

Im folgenden Beispiel wird ein `stackalloc`-Array von ganzen Zahlen in eine Bitmaske initialisiert, für die in jedem Element ein Bit festgelegt ist. Dies stellt die neue Syntax des Initialisierers dar, die ab C# 7.3 verfügbar ist.

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a>Sicherheit

Verwenden Sie wenn möglich <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601>, da der unsichere Code unsicherer ist als sichere Alternativen. Auch bei der Verwendung mit Zeigern aktiviert die Verwendung von `stackalloc` automatisch Funktionen zum Erkennen eines Pufferüberlaufs in der Common Language Runtime (CLR). Wenn ein Pufferüberlauf erkannt wird, wird der Vorgang so schnell wie möglich beendet, damit das Risiko der Ausführung von schädlichem Code verringert wird.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Operatorschlüsselwörter](operator-keywords.md)
- [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md)
