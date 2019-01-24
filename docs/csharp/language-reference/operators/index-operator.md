---
title: '[]-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 01/10/2019
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 948ce238058307631cf0e5a7a5e3d72664233052
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333394"
---
# <a name="-operator-c-reference"></a>[]-Operator (C#-Referenz)

Eckige Klammern (`[]`) werden in der Regel für den Zugriff auf Arrays, Indexer oder Zeigerelemente verwendet.

Weitere Informationen zum Zeigerelementzugriff finden Sie unter [Zugreifen auf ein Arrayelement mit einem Zeiger (C#-Programmierhandbuch)](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).

Sie verwenden eckige Klammern auch, um [Attribute](../../programming-guide/concepts/attributes/index.md) anzugeben:

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="array-access"></a>Arrayzugriff

Im folgenden Beispiel wird der Zugriff auf Elemente des Arrays veranschaulicht:

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Arrays)]

Wenn ein Arrayindex sich außerhalb der Grenzen der entsprechenden Dimension eines Arrays befindet, wird eine <xref:System.IndexOutOfRangeException> ausgelöst.

Wie im vorherigen Beispiel gezeigt, verwenden Sie eckige Klammern auch zur Deklaration eines Arraytyps und Instanziierung von Arrayinstanzen.

Weitere Informationen zu Arrays finden Sie unter [Arrays](../../programming-guide/arrays/index.md).

## <a name="indexer-access"></a>Indexerzugriff

Im folgenden Beispiel wird der Indexerzugriff anhand des .NET <xref:System.Collections.Generic.Dictionary%602>-Typs veranschaulicht:

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Indexers)]

Mit Indexern können Sie Instanzen eines benutzerdefinierten Typs auf ähnliche Weise wie ein Array indizieren. Im Gegensatz zu Arrayindizes, die ganze Zahlen sein müssen, können die Indexerargumente mit einem beliebigen Typ deklariert werden.

Weitere Informationen über Indexer finden Sie unter [Indexer](../../programming-guide/indexers/index.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Elementzugriff `[]` wird nicht als überladbarer Operator betrachtet. Verwenden Sie [Indexer](../../programming-guide/indexers/index.md) zur Unterstützung der Indizierung mit benutzerdefinierten Typen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den Abschnitten [Elementzugriff](~/_csharplang/spec/expressions.md#element-access) und [Zeigerelementzugriff auf](~/_csharplang/spec/unsafe-code.md#pointer-element-access) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [Arrays](../../programming-guide/arrays/index.md)
- [Indexer](../../programming-guide/indexers/index.md)
- [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Attribute](../../programming-guide/concepts/attributes/index.md)