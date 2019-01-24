---
title: ^=-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: 12189d6469a9716d3b7ebcffef23423a75692d1a
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333550"
---
# <a name="-operator-c-reference"></a>^=-Operator (C#-Referenz)

Der XOR-Zuweisungsoperator („exklusives Oder“)

## <a name="remarks"></a>Hinweise

Ein Ausdruck der Form

```csharp
x ^= y
```

wird als ausgewertet,

```csharp
x = x ^ y
```

außer dass `x` nur einmal überprüft wird. Der [Operator ^](xor-operator.md) führt eine bitweise XOR-Operation für integrale Operanden und eine XOR-Operation für [bool](../keywords/bool.md)-Operanden aus.

Der Operator ^= kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [operator ^](xor-operator.md) überladen (weitere Informationen unter [operator](../keywords/operator.md)).

## <a name="example"></a>Beispiel

[!code-csharp[csRefOperators#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#23)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)