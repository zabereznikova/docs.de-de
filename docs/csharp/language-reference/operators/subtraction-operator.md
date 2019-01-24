---
title: '- -Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 8cf6e8871a88e2b37b9531ecbd616289523473c7
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333758"
---
# <a name="--operator-c-reference"></a>-Operator (C#-Referenz)

Der `-`-Operator kann entweder als unärer oder als binärer Operator funktionieren.

## <a name="remarks"></a>Hinweise

Unäre `-`-Operatoren sind für alle numerischen Typen vordefiniert. Das Ergebnis einer unären `-`-Operation für einen numerischen Typ ist die numerische Negation des Operanden.

Binäre `-` Operatoren sind für alle numerischen Typen und Enumerationstypen vordefiniert, um den zweiten Operanden vom ersten zu subtrahieren.

Delegattypen bieten auch einen binären `-`-Operator, der die Delegatentfernung durchführt.

Benutzerdefinierte Typen können die unären `-`- und binären `-`-Operatoren überladen. Weitere Informationen finden Sie unter [operator (C#-Referenz)](../keywords/operator.md).

## <a name="example"></a>Beispiel

[!code-csharp[csRefOperators#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#40)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)