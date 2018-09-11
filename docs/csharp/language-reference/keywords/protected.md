---
title: Schlüsselwort „protected“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: f25e692430f876ec384971079d6d0aa2c97e967b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44197879"
---
# <a name="protected-c-reference"></a>protected (C#-Referenz)

Das `protected`-Schlüsselwort ist ein Zugriffsmodifizierer für Member.

 > Auf dieser Seite wird der Zugriff auf `protected` behandelt. Das Schlüsselwort `protected` ist auch Teil der Zugriffsmodifizierer [`protected internal`](protected-internal.md) und [`private protected`](private-protected.md).

Auf einen geschützten Member kann innerhalb seiner Klasse und von Instanzen abgeleiteter Klasse zugegriffen werden.

Einen Vergleich von `protected` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md).

## <a name="example"></a>Beispiel

Auf einen geschützten Member einer Basisklasse kann in einer abgeleiteten Klasse zugegriffen werden, nur wenn der Zugriff über den Typ der abgeleiteten Klasse erfolgt. Sehen Sie sich z.B. folgenden Codeabschnitt an:

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

Die Anweisung `a.x = 10` generiert einen Fehler, da sie innerhalb der statischen Main-Methode erstellt wird und keine Instanz der Klasse B ist.

Strukturmember können nicht geschützt werden, da die Struktur nicht vererbt werden kann.

## <a name="example"></a>Beispiel

In diesem Beispiel wird die `DerivedPoint`-Klasse von `Point` abgeleitet. Daher können Sie direkt von der abgeleiteten Klasse auf die geschützten Member der Basisklasse zugreifen.

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

Wenn Sie die Zugriffsebenen von `x` und `y` auf [private](private.md) ändern, wird der Compiler die Fehlermeldungen anzeigen:

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Zugriffsmodifizierer](access-modifiers.md)
- [Zugriffsebenen](accessibility-levels.md)
- [Modifizierer](modifiers.md)
- [public](public.md)
- [private](private.md)
- [internal](internal.md)
- [Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://docs.microsoft.com/en-us/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))