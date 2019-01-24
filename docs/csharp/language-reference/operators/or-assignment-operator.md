---
title: '|=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: f4f7806c8679af400a371decd0c367929b3fb81d
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333264"
---
# <a name="-operator-c-reference"></a>|=-Operator (C#-Referenz)

Der OR-Zuweisungsoperator

## <a name="remarks"></a>Hinweise

Ein Ausdruck mit dem Zuweisungsoperator `|=`, z.B.

```csharp
x |= y
```

für die folgende Syntax:

```csharp
x = x | y
```

außer dass `x` nur einmal überprüft wird. Der [Operator &#124;](or-operator.md) führt eine bitweise logische OR-Operation für integrale Operanden und eine logische OR-Operation für boolesche Operanden aus.

Der Operator `|=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [Operator &#124;](or-operator.md) überladen (weitere Informationen unter [operator](../keywords/operator.md)).

## <a name="example"></a>Beispiel

[!code-csharp[csRefOperators#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#10)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)