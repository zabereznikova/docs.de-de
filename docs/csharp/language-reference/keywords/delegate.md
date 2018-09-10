---
title: Delegat (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
ms.openlocfilehash: 7a5f46d137e22da01b2ab6cd3eee57d66c411e8f
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266773"
---
# <a name="delegate-c-reference"></a>Delegat (C#-Referenz)

Die Deklaration eines Delegattyps ähnelt einer Methodensignatur. Er verfügt über einen Rückgabewert und eine beliebige Anzahl Parameter eines beliebigen Typs:

```csharp
public delegate void TestDelegate(string message);
public delegate int TestDelegate(MyType m, long num);
```

Ein `delegate` ist ein Verweistyp, der verwendet werden kann, um eine benannte oder anonyme Methode zu kapseln. Delegaten entsprechen den Funktionszeigern in C++, sind jedoch typsicher und geschützt. Anwendungsmöglichkeiten von Delegaten finden Sie unter [Delegaten](../../../csharp/programming-guide/delegates/index.md) und [Generische Delegaten](../../../csharp/programming-guide/generics/generic-delegates.md).

## <a name="remarks"></a>Hinweise

Delegaten bilden die Grundlage für [Ereignisse](../../../csharp/programming-guide/events/index.md).

Ein Delegat kann instanziiert werden, entweder durch Zuordnen mit einer benannten oder einer anonymen Methode. Weitere Informationen finden Sie unter [Benannte Methoden](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) und [Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).

Der Delegat muss mit einer Methode oder einem Lambda-Ausdruck instanziiert werden, der über einen kompatiblen Rückgabetypen und Eingabeparameter verfügt. Weitere Informationen zum Grad der Varianz, der in der Methodensignatur zulässig ist, finden Sie unter [Varianz bei Delegaten](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md). Für die Verwendung mit anonymen Methoden werden der Delegat und der Code, der mit ihm zugeordnet werden soll, zusammen deklariert. Beide Methoden zur Instanziierung von Delegaten werden in diesem Abschnitt erläutert.

## <a name="example"></a>Beispiel

[!code-csharp[csrefKeywordsTypes#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#8)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
- [Verweistypen](../../../csharp/language-reference/keywords/reference-types.md)  
- [Delegaten](../../../csharp/programming-guide/delegates/index.md)  
- [Ereignisse](../../../csharp/programming-guide/events/index.md)  
- [Delegate mit benannten im Vergleich zu anonymen Methoden](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
- [Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
