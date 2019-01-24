---
title: -=-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 3b6890be4460a599a5d2f5f5f6ee1627be933f0b
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333329"
---
# <a name="--operator-c-reference"></a>-=-Operator (C#-Referenz)

Der Subtraktionszuweisungsoperator.

## <a name="remarks"></a>Hinweise

Ein Ausdruck mit dem Zuweisungsoperator `-=`, z.B.

```csharp
x -= y
```

 für die folgende Syntax:

```csharp
x = x - y
```

außer dass `x` nur einmal überprüft wird. Die Bedeutung des [Operators -](subtraction-operator.md) hängt von den Typen `x` und `y` (Subtraktion für nummerische Operanden, Delegatentfernung für Delegatoperatoren usw.) ab.

Der Operator `-=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[- Operator](subtraction-operator.md) überladen (siehe [Operator](../keywords/operator.md)).

Der Operator -= wird auch in C# verwendet, um ein Ereignisabonnement zu kündigen. Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="example"></a>Beispiel

[!code-csharp[csRefOperators#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#6)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
