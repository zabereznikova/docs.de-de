---
title: Overloads
ms.date: 07/20/2015
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
ms.openlocfilehash: 44823b409cfa81dc889aabacf101fac90bf851e0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351407"
---
# <a name="overloads-visual-basic"></a>Overloads (Visual Basic)

Gibt an, dass eine Eigenschaft oder Prozedur eine Eigenschaft oder Prozedur bzw. mehrere mit dem gleichen Namen neu deklariert.

## <a name="remarks"></a>Hinweise

Bei der *Überladung* wird die Bereitstellung von mehr als einer Definition für eine bestimmte Eigenschaft oder einen bestimmten Prozedur Namen im selben Bereich beschrieben. Das erneute Deklarieren einer Eigenschaft oder Prozedur mit einer anderen Signatur wird manchmal als ausblenden *nach Signatur*bezeichnet.

## <a name="rules"></a>Regeln

- **Deklarations Kontext.** Sie können `Overloads` nur in einer Eigenschaft oder Prozedur Deklarations Anweisung verwenden.

- **Kombinierte modifiziererer.** Sie können `Overloads` [nicht mit](../../../visual-basic/language-reference/modifiers/shadows.md) Shadowing in derselben Prozedur Deklaration angeben.

- **Erforderliche Unterschiede.** Die *Signatur* in dieser Deklaration muss sich von der Signatur jeder Eigenschaft oder Prozedur unterscheiden, die Sie über lädt. Die Signatur besteht aus der Eigenschaft oder dem Prozedurnamen und dem Folgenden:

  - der Anzahl der Parameter

  - Der Reihenfolge der Parameter

  - der Datentypen der Parameter

  - der Anzahl der Typparameter (für eine generische Prozedur)

  - der Rückgabetyp (nur für eine Konvertierungsoperatorprozedur)

  Alle Überladungen müssen denselben Namen aufweisen. Jede muss sich jedoch von allen anderen in mindestens einem der vorstehenden Punkte unterscheiden. Dadurch kann der Compiler unterscheiden, welche Version verwendet werden muss, wenn der Code die Eigenschaft oder Prozedur aufruft.

- **Unzulässige Unterschiede.** Das Ändern von mindestens einem der folgenden Punkte ist für das Überladen einer Eigenschaft oder Prozedur nicht gültig, da sie kein Bestandteil der Signatur sind:

  - ob ein Wert (für eine Prozedur) zurückgegeben wird

  - der Datentyp des Rückgabewerts (mit Ausnahme eines Konvertierungsoperators)

  - die Namen der Parameter oder Typparameter

  - die Einschränkungen hinsichtlich der Typparameter (für eine generische Prozedur)

  - Parametermodifiziererschlüsselwörter (wie `ByRef` oder `Optional`)

  - Eigenschaft oder Prozedurmodifiziererschlüsselwörter (wie `Public` oder `Shared`)

- **Optionaler Modifizierer.** Sie müssen den `Overloads` Modifizierer nicht verwenden, wenn Sie mehrere überladene Eigenschaften oder Prozeduren in derselben Klasse definieren. Wenn Sie jedoch `Overloads` in einer der Deklarationen verwenden, müssen Sie sie in allen davon verwenden.

- **Shadoading und überladen.** `Overloads` können auch verwendet werden, um ein vorhandenes Element oder einen Satz überladener Member in einer Basisklasse zu überschatten. Wenn Sie `Overloads` auf diese Art und Weise verwenden, deklarieren Sie die Eigenschaft oder Methode mit demselben Namen und derselben Parameterliste als Basisklassenmember, und Sie stellen das `Shadows`-Schlüsselwort nicht bereit.

Beim Verwenden von `Overrides` fügt der Compiler implizit `Overloads` hinzu, sodass Ihre Bibliotheks-APIs leichter mit C# verwendet werden können.

Der `Overloads`-Modifizierer kann in folgenden Kontexten verwendet werden:

- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)

- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)

- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)

- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>Siehe auch

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Prozedurüberladung](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Gewusst wie: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
