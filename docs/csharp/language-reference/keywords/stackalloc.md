---
title: stackalloc (C#-Referenz)
ms.date: 04/12/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c4cde254bb6a5601d10619c4a3bd2f00f1f146d3
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="stackalloc-c-reference"></a>stackalloc (C#-Referenz)
Das Schlüsselwort `stackalloc` wird in unsicherem Codekontext verwendet, um dem Stapel einen Speicherblock zuzuweisen.

```csharp
int* block = stackalloc int[100];
```

## <a name="remarks"></a>Hinweise

Das Schlüsselwort ist nur in lokalen Variableninitialisierern gültig. Folgender Code verursacht Compilerfehler.

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
```

Ab C# 7.3 können Sie die Syntax des Arrayinitialisierers für `stackalloc`-Arrays verwenden. Alle nachfolgenden Deklarationen deklarieren ein Array mit drei Elementen, dessen Werte die ganzen Zahlen `1`, `2` und `3` darstellen:

```csharp
// Valid starting with C# 7.3
int* first = stackalloc int[3] { 1, 2, 3 };
int* second = stackalloc int[] { 1, 2, 3 };
int* third = stackalloc[] { 1, 2, 3 };
```

Da Zeigertypen beteiligt sind, benötigt `stackalloc` einen [unsafe](unsafe.md)-Kontext. Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md). 

Genau wie [_alloca](/cpp/c-runtime-library/reference/alloca) befindet sich `stackalloc` in der C-Laufzeitbibliothek.

## <a name="examples"></a>Beispiele

Im folgenden Beispiel werden die ersten 20 Zahlen der Fibonacci-Folge berechnet und angezeigt. Jede Zahl bildet die Summe der beiden vorherigen Zahlen. Im Code wird dem Stapel, nicht dem Heap, ein Speicherblock zugewiesen, der groß genug ist, um 20 Elemente vom Typ `int` zu enthalten. Die Adresse des Blocks wird im Zeiger `fib` gespeichert. Dieser Speicher unterliegt nicht der automatischen Speicherbereinigung und muss daher nicht (mithilfe von [fixed](fixed-statement.md)) angeheftet werden. Die Lebensdauer des Speicherblocks ist auf die Lebensdauer der definierenden Methode begrenzt. Sie können den Speicher nicht freigeben, bevor die Methode zurückgibt.

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

Im folgenden Beispiel wird ein `stackalloc`-Array von ganzen Zahlen in eine Bitmaske initialisiert, für die in jedem Element ein Bit festgelegt ist. Dies stellt die neue Syntax des Initialisierers dar, die ab C# 7.3 verfügbar ist.

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a>Sicherheit

Unsicherer Code ist unsicherer als sichere Alternativen. Allerdings werden mit der Verwendung von `stackalloc` automatisch Funktionen zum Erkennen eines Pufferüberlaufs in der Common Language Runtime (CLR) aktiviert. Wenn ein Pufferüberlauf erkannt wird, wird der Vorgang so schnell wie möglich beendet, damit das Risiko der Ausführung von schädlichem Code verringert wird.

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
