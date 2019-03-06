---
title: sein. -Operator – C#-Referenz
ms.custom: seodec18
ms.date: 02/25/2019
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: 2661676d53deb874c5e5a90b4443b301730e09df
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836460"
---
# <a name="-operator-c-reference"></a>sein. operator (C#-Referenz)

Der Punkt (`.`) wird normalerweise für den Memberzugriff verwendet.

Sie verwenden das `.`-Token für den Zugriff auf einen Member eines Namespace oder eines Typs, wie die folgenden Beispiele veranschaulichen:

- Verwenden Sie `.` für den Zugriff auf einen geschachtelten Namespace innerhalb eines Namespace, wie im folgenden Beispiel einer [`using`-Anweisung](../keywords/using-directive.md) gezeigt:

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#NestedNamespace)]

- Verwenden Sie `.`, um einen *qualifizierten Namen* zu bilden, um auf einen Typ innerhalb eines Namespace zuzugreifen, wie im folgenden Code gezeigt:

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#QualifiedName)]

  Verwenden Sie die [`using`-Anweisung](../keywords/using-directive.md), um die Verwendung qualifizierter Namen optional zu machen.

- Verwenden Sie `.` für den Zugriff auf [Typmember](../../programming-guide/classes-and-structs/index.md#members), statische und nicht statische, wie im folgenden Code gezeigt:

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#TypeMemberAccess)]

Sie können auch `.` verwenden, um eine [Erweiterungsmethode](../../programming-guide/classes-and-structs/extension-methods.md) aufzurufen.

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Der Operator `.` kann nicht überladen werden.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Memberzugriff](~/_csharplang/spec/expressions.md#member-access) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [?.- und ?[]-Operatoren](null-conditional-operators.md)