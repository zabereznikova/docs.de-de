---
description: public-Schlüsselwort – C#-Referenz
title: public-Schlüsselwort – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 90c1d2a1d9efcdf57f914f4318bf7a743d3f37ec
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938467"
---
# <a name="public-c-reference"></a>public (C#-Referenz)

Das Schlüsselwort `public` ist ein Zugriffsmodifizierer für Typen und Typmember. Der öffentlicher Zugriff ist die eingeschränkteste Zugriffsebene. Es gibt keine Einschränkungen für den Zugriff auf öffentliche Member, wie im folgenden Beispiel veranschaulicht:

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

Unter [Access Modifiers (Zugriffsmodifizierer)](../../programming-guide/classes-and-structs/access-modifiers.md) und [Accessibility Levels (Zugriffsebenen)](accessibility-levels.md) finden Sie weitere Informationen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Klassen deklariert, `PointTest` und `Program`. Auf die öffentlichen Member `x` und `y` von `PointTest` wird direkt von `Program` zugegriffen.

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

Wenn Sie die Zugriffsebene `public` auf [private](private.md) (privat) oder [protected](protected.md) (geschützt) festlegen, wird die folgende Fehlermeldung angezeigt:

'PointTest.y' is inaccessible due to its protection level (Der Zugriff auf ‚PointTest.y‘ ist aufgrund der Sicherheitsebene nicht möglich).

## <a name="c-language-specification"></a>C#-Sprachspezifikation  

Weitere Informationen finden Sie unter [Deklarierte Barrierefreiheit](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [Zugriffsmodifizierer](../../programming-guide/classes-and-structs/access-modifiers.md)
- [C#-Schlüsselwörter](index.md)
- [Zugriffsmodifizierer](access-modifiers.md)
- [Zugriffsebenen](accessibility-levels.md)
- [Modifizierer](index.md)
- [private](private.md)
- [protected](protected.md)
- [internal](internal.md)
