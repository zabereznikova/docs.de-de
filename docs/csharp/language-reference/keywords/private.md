---
title: private-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: 19e2925cd65cc9c68ff50d370398a4f401275940
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422592"
---
# <a name="private-c-reference"></a>private (C#-Referenz)

Das `private`-Schlüsselwort ist ein Zugriffsmodifizierer für Member.

> Auf dieser Seite wird der Zugriff auf `private` behandelt. Das Schlüsselwort `private` ist auch Teil des Zugriffsmodifizierers [`private protected`](./private-protected.md).

Privater-Zugriff ist die am wenigsten eingeschränkte Zugriffsebene. Private Member sind nur innerhalb der Klasse oder Struktur, in der sie, wie im folgenden Beispiel, deklariert werden:

```csharp
class Employee
{
    private int i;
    double d;   // private access by default
}
```

Geschachtelte Typen im gleichen Text können auch auf diese privaten Member zugreifen.

Es ist ein Kompilierzeitfehler auf einen privaten Member außerhalb der Klasse oder Struktur, in der sie deklariert ist, zu verweisen.

Einen Vergleich von `private` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md) und [Zugriffsmodifizierer](../../programming-guide/classes-and-structs/access-modifiers.md).

## <a name="example"></a>Beispiel

In diesem Beispiel enthält die `Employee`-Klasse zwei private Datenmember, `name` und `salary`. Als private Member können nur Membermethoden auf sie zugreifen. Die öffentlichen Methoden `GetName` und `Salary` werden hinzugefügt, um gesteuerten Zugriff auf die privaten Member zu ermöglichen. Auf den `name`-Member wird über eine öffentliche Methode zugegriffen, und auf den `salary`-Member wird über eine öffentliche schreibgeschützte Eigenschaft zugegriffen. (Weitere Informationen finden Sie unter [Eigenschaften](../../programming-guide/classes-and-structs/properties.md).)

[!code-csharp[csrefKeywordsModifiers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#10)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation  

Weitere Informationen finden Sie unter [Deklarierte Barrierefreiheit](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Zugriffsmodifizierer](access-modifiers.md)
- [Zugriffsebenen](accessibility-levels.md)
- [Modifizierer](index.md)
- [public](public.md)
- [protected](protected.md)
- [internal](internal.md)
