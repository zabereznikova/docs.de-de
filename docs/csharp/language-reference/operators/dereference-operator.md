---
title: -&gt;-Operator (C#-Referenz)
ms.date: 11/26/2018
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: 178724ede105d809bd812461121a38d5a0e90517
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144129"
---
# <a name="-gt-operator-c-reference"></a>-&gt;-Operator (C#-Referenz)

Der Zeigermember-Zugriffsoperator `->` kombiniert Zeigerdereferenzierung mit Memberzugriff.

Wenn `x` ein Zeiger des Typs `T*` und `y` ein Member von `T` ist, auf den zugegriffen werden kann, dann ist ein Ausdruck der Form

```csharp
x->y
```

für die folgende Syntax:

```csharp
(*x).y
```

Der `->`-Operator erfordert [unsicheren](../keywords/unsafe.md) Kontext.

Weitere Informationen finden Sie unter [Gewusst wie: Zugreifen auf einen Member mit einem Zeiger](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Operator `->` kann nicht überladen werden.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Zeigermemberzugriff](~/_csharplang/spec/unsafe-code.md#pointer-member-access) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md)
