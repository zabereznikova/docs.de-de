---
title: new-Operator – C#-Referenz
ms.date: 06/25/2019
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: ed18c42cd28412a967c94a65c2a92b0b75097b52
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199728"
---
# <a name="new-operator-c-reference"></a>new-Operator (C#-Referenz)

Der `new`-Operator erstellt eine neue Instanz eines Typs.

Sie können das Schlüsselwort `new` auch als einen [Memberdeklarationsmodifizierer](../keywords/new-modifier.md) oder als [Einschränkung eines generischen Typs](../keywords/new-constraint.md) verwenden.

## <a name="constructor-invocation"></a>Konstruktoraufruf

Um eine neue Instanz eines Typs zu erstellen, rufen Sie in der Regel einen der [Konstruktoren](../../programming-guide/classes-and-structs/constructors.md) dieses Typs mit dem `new`-Operator auf:

[!code-csharp-interactive[invoke constructor](snippets/NewOperator.cs#Constructor)]

Sie können einen [Objekt- oder Auflistungsinitialisierer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) mit dem `new`-Operator verwenden, um ein Objekt in einer Anweisung zu instanziieren und zu initialisieren, wie das folgende Beispiel zeigt:

[!code-csharp-interactive[constructor with initializer](snippets/NewOperator.cs#ConstructorWithInitializer)]

## <a name="array-creation"></a>Arrayerstellung

Sie können den `new`-Operator auch verwenden, um eine Arrayinstanz zu erstellen, wie das folgende Beispiel zeigt:

[!code-csharp-interactive[create array](snippets/NewOperator.cs#Array)]

Verwenden Sie die Arrayinitialisierungssyntax, um eine Arrayinstanz zu erstellen und sie mit Elementen in einer Anweisung zu auszufüllen. Im folgenden Beispiel werden verschiedene Möglichkeiten dafür veranschaulicht:

[!code-csharp-interactive[initialize array](snippets/NewOperator.cs#ArrayInitialization)]

Weitere Informationen zu Arrays finden Sie unter [Arrays](../../programming-guide/arrays/index.md).

## <a name="instantiation-of-anonymous-types"></a>Instanziierung von anonymen Typen

Um eine Instanz eines [anonymen Typs](../../programming-guide/classes-and-structs/anonymous-types.md) zu erstellen, verwenden Sie die Syntax für die Initialisierung von `new`-Operatoren und -Objekten:

[!code-csharp-interactive[anonymous type](snippets/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a>Zerstörung von Typinstanzen

Sie müssen keine zuvor angelegten Typinstanzen zerstören. Instanzen sowohl von Verweis- als auch von Werttypen werden automatisch zerstört. Instanzen von Werttypen werden zerstört, sobald der sie enthaltende Kontext zerstört wird. Instanzen von Verweistypen werden vom [Garbage Collector](../../../standard/garbage-collection/index.md) zu einem unbestimmten Zeitpunkt zerstört, nachdem der letzte Verweis auf sie entfernt wurde.

Bei Typinstanzen, die nicht verwaltete Ressourcen wie beispielsweise ein Dateihandle enthalten, ist eine deterministische Bereinigung empfehlenswert, um sicherzustellen, dass die darin enthaltenen Ressourcen so bald wie möglich freigegeben werden. Weitere Informationen finden Sie im Artikel zum <xref:System.IDisposable?displayProperty=nameWithType>API-Verweis und der [using-Anweisung](../keywords/using-statement.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann den `new`-Operator nicht überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Der new-Operator](~/_csharplang/spec/expressions.md#the-new-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [Objekt- und Elementinitialisierer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
