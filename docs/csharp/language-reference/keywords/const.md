---
title: const-Schlüsselwort – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
ms.openlocfilehash: 812aeb331b6dd333075d19076a896246ecc5b374
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713677"
---
# <a name="const-c-reference"></a>const (C#-Referenz)

Sie verwenden das `const`-Schlüsselwort, um ein konstantes Feld oder eine konstante lokale Variable zu deklarieren. Konstante Felder und lokale Felder sind keine Variablen und können daher nicht geändert werden. Konstanten können Nummern, boolesche Werte, Zeichenfolgen oder ein NULL-Verweis sein. Erstellen Sie keine Konstante, um Informationen darzustellen, bei denen Sie davon ausgehen, dass sie sich einmal ändern. Verwenden Sie beispielsweise kein konstantes Feld, um den Preis einer Dienstleistung, einer Produktversionsnummer oder den Markennamen eines Unternehmens zu speichern. Diese Werte können sich im Laufe der Zeit ändern, und da Compiler Konstanten weitergeben, muss anderer Code, der mit Ihren Bibliotheken kompiliert wird, neu kompiliert werden, damit die Änderungen sichtbar werden. Weitere Informationen finden Sie auch unter dem [readonly](./readonly.md)-Schlüsselwort. Zum Beispiel:

```csharp
const int X = 0;
public const double GravitationalConstant = 6.673e-11;
private const string ProductName = "Visual C#";
```

## <a name="remarks"></a>Hinweise

Der Typ einer Konstantendeklaration gibt den Typ der Member an, die durch die Deklaration eingeführt werden. Der Initialisierer einer konstanten lokalen Variable oder eines konstanten Felds muss ein konstanter Ausdruck sein, der implizit in den Zieltyp konvertiert werden kann.

Ein konstanter Ausdruck ist ein Ausdruck, der während der Kompilierung vollständig ausgewertet werden kann. Daher sind `string` und ein NULL-Verweis die einzig möglichen Werte für Verweistypkonstanten.

In der Konstantendeklaration können mehrere Konstanten deklariert werden, z. B.:

```csharp
public const double X = 1.0, Y = 2.0, Z = 3.0;
```

Der `static`-Modifizierer ist in einer Konstantendeklaration nicht zulässig.

Eine Konstante kann wie folgt einen Teil eines konstanten Ausdrucks darstellen:

```csharp
public const int C1 = 5;
public const int C2 = C1 + 100;
```

> [!NOTE]
> Das [readonly](./readonly.md)-Schlüsselwort unterscheidet sich vom `const`-Schlüsselwort. Ein `const`-Feld kann nur bei der Deklaration des Felds initialisiert werden. Ein `readonly`-Feld kann entweder bei der Deklaration oder in einem Konstruktor initialisiert werden. Daher können `readonly`-Felder abhängig vom verwendeten Konstruktor über unterschiedliche Werte verfügen. Außerdem ist ein `const`-Feld eine Kompilierzeitkonstante, während ein `readonly`-Feld für Laufzeitkonstanten verwendet werden kann, wie in der folgenden Codezeile: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`.

## <a name="example"></a>Beispiel

[!code-csharp[csrefKeywordsModifiers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#5)]

## <a name="example"></a>Beispiel

In diesem Beispiel wird das Verwenden von Konstanten als lokale Variablen demonstriert.

[!code-csharp[csrefKeywordsModifiers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#6)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](./index.md)
- [Modifizierer](index.md)
- [readonly](./readonly.md)
