---
title: Overrides
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 04f1cb27d6a8366c2dd13f8fdc1d975d382f1cfd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351388"
---
# <a name="overrides-visual-basic"></a>Overrides (Visual Basic)

Gibt an, dass eine Eigenschaft oder Prozedur eine Eigenschaft oder Prozedur mit dem gleichen Namen überschreibt, die von einer Basisklasse geerbt wurde.

## <a name="rules"></a>Regeln

- **Declaration Context.** You can use `Overrides` only in a property or procedure declaration statement.

- **Combined Modifiers.** You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration. Da ein überschreibendes Element implizit überschreibbar ist, können Sie `Overridable` nicht mit `Overrides` kombinieren.

- **Matching Signatures.** The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides. Das bedeutet, dass die Anzahl, die Reihenfolge und die Datentypen der Parameter in den Parameterlisten gleich sein müssen.

  Neben der Signatur müssen auch die folgenden Elemente der überschreibenden Deklaration genau übereinstimmen:

  - Die Zugriffsebene

  - Der Rückgabetyp, falls vorhanden

- **Generic Signatures.** Bei einer generischen Prozedur umfasst die Signatur die Anzahl der Typparameter. Daher muss die überschreibende Deklaration auch in dieser Hinsicht mit der Basisklassenversion übereinstimmen.

- **Additional Matching.** Diese Deklaration muss nicht nur in Bezug auf die Signatur, sondern auch in folgenden Punkten mit der Basisklassenversion übereinstimmen:

  - Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))

  - Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))

  - Einschränkungslisten für jeden Typparameter einer generischen Prozedur

- **Shadowing and Overriding.** Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen. For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).

Beim Verwenden von `Overrides` fügt der Compiler implizit `Overloads` hinzu, sodass Ihre Bibliotheks-APIs leichter mit C# verwendet werden können.

Der `Overrides`-Modifizierer kann in folgenden Kontexten verwendet werden:

- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)

- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)

- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>Siehe auch

- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)
- [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Typliste](../../../visual-basic/language-reference/statements/type-list.md)
