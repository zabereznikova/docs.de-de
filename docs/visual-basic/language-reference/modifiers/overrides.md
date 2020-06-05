---
title: Überschreibt
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
ms.openlocfilehash: 657f838b2959a5b6a7cef5ff18295a4ada709e9a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392027"
---
# <a name="overrides-visual-basic"></a>Overrides (Visual Basic)

Gibt an, dass eine Eigenschaft oder Prozedur eine Eigenschaft oder Prozedur mit dem gleichen Namen überschreibt, die von einer Basisklasse geerbt wurde.

## <a name="rules"></a>Regeln

- **Deklarationskontext.** Sie können `Overrides` nur in einer Deklarations Anweisung für eine Eigenschaft oder Prozedur verwenden.

- **Kombinierte Modifizierer.** Sie können nicht `Overrides` mit `Shadows` oder `Shared` in derselben Deklaration angeben. Da ein überschreibendes Element implizit überschreibbar ist, können Sie `Overridable` nicht mit `Overrides` kombinieren.

- **Übereinstimmende Signaturen.** Die Signatur dieser Deklaration muss genau mit der *Signatur* der Eigenschaft oder Prozedur übereinstimmen, die Sie überschreibt. Das bedeutet, dass die Anzahl, die Reihenfolge und die Datentypen der Parameter in den Parameterlisten gleich sein müssen.

  Neben der Signatur müssen auch die folgenden Elemente der überschreibenden Deklaration genau übereinstimmen:

  - Die Zugriffsebene

  - Der Rückgabetyp, falls vorhanden

- **Generische Signaturen.** Bei einer generischen Prozedur umfasst die Signatur die Anzahl der Typparameter. Daher muss die überschreibende Deklaration auch in dieser Hinsicht mit der Basisklassenversion übereinstimmen.

- **Zusätzliche Übereinstimmung.** Diese Deklaration muss nicht nur in Bezug auf die Signatur, sondern auch in folgenden Punkten mit der Basisklassenversion übereinstimmen:

  - Modifizierer auf Zugriffsebene (z. b. [Public](public.md))

  - Übergabe Mechanismus jedes Parameters ([ByVal](byval.md) oder [ByRef](byref.md))

  - Einschränkungslisten für jeden Typparameter einer generischen Prozedur

- **Shadowing und Überschreiben.** Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen. Weitere Informationen finden Sie unter [shadowingin Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).

Beim Verwenden von `Overrides` fügt der Compiler implizit `Overloads` hinzu, sodass Ihre Bibliotheks-APIs leichter mit C# verwendet werden können.

Der `Overrides`-Modifizierer kann in folgenden Kontexten verwendet werden:

- [Function-Anweisung](../statements/function-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Sub-Anweisung](../statements/sub-statement.md)

## <a name="see-also"></a>Weitere Informationen

- [MustOverride](mustoverride.md)
- [NotOverridable](notoverridable.md)
- [Overrides](overridable.md)
- [Schlüsselwörter](../keywords/index.md)
- [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
- [Generische Typen in Visual Basic (Visual Basic)](../../programming-guide/language-features/data-types/generic-types.md)
- [Type List](../statements/type-list.md)
