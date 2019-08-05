---
title: 'Operator „::“: C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: c494e8dbb18f44ce5520b21800a21d3feb03da59
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631364"
---
# <a name="-operator-c-reference"></a>Operator „::“ (C#-Referenz)

Der Namespacealias-Qualifizierer (`::`) wird verwendet, um nach Bezeichnern zu suchen. Er befindet sich immer zwischen zwei Bezeichnern, wie im folgenden Beispiel:

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

Der Operator `::` kann auch mit einer *Alias-Direktive* verwendet werden:

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a>Anmerkungen

Der Namespacealias-Qualifizierer kann `global` sein. Dadurch wird eine Suche im globalen Namespace anstatt Namespacealias aufgerufen.

## <a name="for-more-information"></a>Weitere Informationen

Ein Beispiel zur Verwendung des `::`-Operators finden Sie im folgenden Abschnitt:

- [Vorgehensweise: Verwenden des globalen Namespacealias](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [.-Operator](member-access-operators.md#member-access-operator-)
- [extern alias](../keywords/extern-alias.md)
