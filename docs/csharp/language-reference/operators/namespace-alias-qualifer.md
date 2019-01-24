---
title: ::-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 2618131f27271e7c06cb6d425fc22b5bd9750c49
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333316"
---
# <a name="-operator-c-reference"></a>::-Operator (C#-Referenz)

Der Namespacealias-Qualifizierer (`::`) wird verwendet, um nach Bezeichnern zu suchen. Er befindet sich immer zwischen zwei Bezeichnern, wie im folgenden Beispiel:

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

Der Operator `::` kann auch mit einer *Alias-Direktive* verwendet werden:

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a>Hinweise

Der Namespacealias-Qualifizierer kann `global` sein. Dadurch wird eine Suche im globalen Namespace anstatt Namespacealias aufgerufen.

## <a name="for-more-information"></a>Weitere Informationen

Ein Beispiel zur Verwendung des `::`-Operators finden Sie im folgenden Abschnitt:

- [Vorgehensweise: Verwenden des globalen Namespacealias](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [Namespaceschlüsselwörter](../keywords/namespace-keywords.md)
- [.-Operator](member-access-operator.md)
- [extern alias](../keywords/extern-alias.md)