---
description: var – C#-Referenz
title: var – C#-Referenz
ms.date: 10/02/2020
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: d04bea9bcf5be726d3e81a1a53abed31f59330a0
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608711"
---
# <a name="var-c-reference"></a>var (C#-Referenz)

Ab C# 3 können Variablen, die im Methodenbereich deklariert wurden, den impliziten „Typ“ `var` haben. Eine implizit typisierte lokale Variable ist stark typisiert, als hätten Sie den Typ selbst deklariert. Tatsächlich legt der Compiler den Typ fest. Die folgenden beiden `i`-Aktivitäten sind funktional äquivalent:

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

> [!IMPORTANT]
> Wenn `var` mit aktivierten [Verweistypen verwendet wird, die Nullwerte zulassen](../builtin-types/nullable-reference-types.md), impliziert dies immer einen Verweistyp, der Nullwerte zulässt, auch wenn der Ausdruckstyp diese zulässt.

Das `var`-Schlüsselwort wird häufig verwendet, wenn Konstruktoraufrufausdrücke verwendet werden. Durch die Verwendung von `var` können Sie einen Typnamen in einer Variablendeklaration und Objektinstanziierung nicht wiederholen, wie im folgenden Beispiel gezeigt:

```csharp
var xs = new List<int>();
```

Ab C# 9.0 können Sie als Alternative einen als Ziel typisierten [`new`-Ausdruck](../operators/new-operator.md) verwenden:

```csharp
List<int> xs = new();
List<int>? ys = new();
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Abfrageausdrücke gezeigt. Im ersten Ausdruck in das Verwenden von `var` erlaubt aber nicht erforderlich, da der Typ des Abfrageergebnisses explizit als `IEnumerable<string>` angegeben werden kann. Im zweiten Ausdruck ermöglicht `var`, dass das Ergebnis eine Auflistung von anonymen Typen ist und dass auf die Namen dieser Typen nicht zugegriffen werden kann. Nur der Compiler kann darauf zugreifen. Durch die Verwendung von `var` wird die Voraussetzung beseitigt, eine neue Klasse für das Ergebnis erstellen zu müssen. Beachten Sie, dass die `foreach`-Iterationsvariable `item` im zweiten Beispiel auch implizit typisiert sein muss.

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Implizit typisierte lokale Variablen](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
- [Type relationships in LINQ query operations (Typbeziehungen in LINQ-Abfragevorgängen)](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
