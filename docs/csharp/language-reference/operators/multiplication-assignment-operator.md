---
title: '*=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 2038f3b55d46f3503496275b3d25b17663b8c1db
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333433"
---
# <a name="-operator-c-reference"></a>Operator \*= (C#-Referenz)

Der binäre Multiplikationszuweisungsoperator

## <a name="remarks"></a>Hinweise

Ein Ausdruck mit dem Zuweisungsoperator `*=`, z.B.

```csharp
x *= y
```

für die folgende Syntax:

```csharp
x = x * y
```

außer dass `x` nur einmal überprüft wird. Der [\*-Operator](multiplication-operator.md) ist für numerische Typen für die Multiplikation vordefiniert.

Der `*=`-Operator kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [\*-Operator](multiplication-operator.md) überladen (siehe [Operator](../keywords/operator.md)).

## <a name="example"></a>Beispiel

[!code-csharp[csRefOperators#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#13)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
