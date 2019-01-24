---
title: '* -Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: f4490c4632d9344eb879ea55c20787b838781d91
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333732"
---
# <a name="-operator-c-reference"></a>*-Operator (C#-Referenz)

Der Multiplikationsoperator (`*`) berechnet das Produkt seiner Operanden. Alle numerischen Typen besitzen vordefinierte Multiplikationsoperatoren.

`*` dient auch als Dereferenzierungsoperator, der das Lesen und Schreiben in einen Zeiger ermöglicht.

## <a name="remarks"></a>Hinweise

Der `*`-Operator wird auch verwendet, um Zeigertypen zu deklarieren und Zeiger zu dereferenzieren. Dieser Operator kann nur in nicht sicheren Kontexten verwendet werden, gekennzeichnet durch die Verwendung des [unsafe](../keywords/unsafe.md)-Schlüsselworts und erfordert die Compileroption [/unsafe](../compiler-options/unsafe-compiler-option.md).  Die englischen Begriffe „dereference operator“ und „indirection operator“ bezeichnen beide den Dereferenzierungsoperator.

Benutzerdefinierte Typen können den binären `*`-Operator überladen (weitere Informationen finden Sie unter [Operator](../keywords/operator.md)). Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.

## <a name="example"></a>Beispiel

[!code-csharp-interactive[csRefOperators#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#50)]

## <a name="example"></a>Beispiel

[!code-csharp[csRefOperators#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#51)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md)
- [C#-Operatoren](index.md)