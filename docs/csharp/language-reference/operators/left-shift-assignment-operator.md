---
title: <<=-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: 0a005efa19be24f9adbf9031f562a30f9c1b0e34
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258733"
---
# <a name="-operator-c-reference"></a>\<\<=-Operator (C#-Referenz)

Der Linksschiebezuweisungs-Operator

## <a name="remarks"></a>Hinweise

Ein Ausdruck der Form

```csharp
x <<= y
```

wird als ausgewertet,

```csharp
x = x << y
```

außer dass `x` nur einmal überprüft wird. Der [Operator <<](left-shift-operator.md) verschiebt `x` um die von `y` angegebenen Schritte nach links.

Der Operator `<<=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[<< operator](left-shift-operator.md) überladen (weitere Informationen unter [Operator](../keywords/operator.md)).

## <a name="example"></a>Beispiel

[!code-csharp[csRefOperators#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#12)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
