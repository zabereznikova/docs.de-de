---
title: '&gt;&gt;=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 02a9559a5c4086eeed09094c15c3620366ffad8c
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333686"
---
# <a name="gtgt-operator-c-reference"></a>&gt;&gt;=-Operator (C#-Referenz)

Der Rechtsschiebezuweisungsoperator.

## <a name="remarks"></a>Hinweise

Ein Ausdruck der Form

```csharp
x >>= y
```

wird als ausgewertet,

```csharp
x = x >> y
```

außer dass `x` nur einmal überprüft wird. Der [>>-Operator](right-shift-operator.md) verschiebt `x` um einen durch `y` angegebenen Wert nach rechts.

Der >>=-Operator kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [>>-Operator](right-shift-operator.md) überladen (siehe [Operator](../keywords/operator.md)).

## <a name="example"></a>Beispiel

[!code-csharp[csRefOperators#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#11)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)