---
title: '|-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 185ea3aabff4794ec08cca541773dbec3574ab4b
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333511"
---
# <a name="-operator-c-reference"></a>|-Operator (C#-Referenz)

Binäre `|`-Operatoren sind für integrale Typen und `bool` vordefiniert. Für integrale Typen berechnet `|` die bitweise OR-Operation der Operanden. Für `bool` Operanden berechnet `|` die logische OR-Operator seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `false` ist, wenn beide Operanden `false` sind.

## <a name="remarks"></a>Hinweise

Im Gegensatz zum [bedingten OR-Operator](conditional-or-operator.md) `||` wertet der binäre `|`-Operator beide Operanden unabhängig vom Wert des ersten Operanden aus.

Benutzerdefinierte Typen können den Operator `|` überladen (weitere Informationen unter [operator](../keywords/operator.md)).

## <a name="example"></a>Beispiel

 [!code-csharp[csRefOperators#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#31)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)