---
title: Überlädt
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
ms.openlocfilehash: bd0931cab520f8580c0d7473a44e350752e287bb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392105"
---
# <a name="overloads-visual-basic"></a>Overloads (Visual Basic)

Gibt an, dass eine Eigenschaft oder Prozedur eine Eigenschaft oder Prozedur bzw. mehrere mit dem gleichen Namen neu deklariert.

## <a name="remarks"></a>Bemerkungen

Bei der *Überladung* wird die Bereitstellung von mehr als einer Definition für eine bestimmte Eigenschaft oder einen bestimmten Prozedur Namen im selben Bereich beschrieben. Das erneute Deklarieren einer Eigenschaft oder Prozedur mit einer anderen Signatur wird manchmal als ausblenden *nach Signatur*bezeichnet.

## <a name="rules"></a>Regeln

- **Deklarationskontext.** Sie können `Overloads` nur in einer Deklarations Anweisung für eine Eigenschaft oder Prozedur verwenden.

- **Kombinierte Modifizierer.** Sie können nicht `Overloads` mit Shadowing in derselben Prozedur Deklaration angeben. [Shadows](shadows.md)

- **Erforderliche Unterschiede.** Die *Signatur* in dieser Deklaration muss sich von der Signatur jeder Eigenschaft oder Prozedur unterscheiden, die Sie über lädt. Die Signatur besteht aus der Eigenschaft oder dem Prozedurnamen und dem Folgenden:

  - der Anzahl der Parameter

  - Der Reihenfolge der Parameter

  - der Datentypen der Parameter

  - der Anzahl der Typparameter (für eine generische Prozedur)

  - der Rückgabetyp (nur für eine Konvertierungsoperatorprozedur)

  Alle Überladungen müssen denselben Namen aufweisen. Jede muss sich jedoch von allen anderen in mindestens einem der vorstehenden Punkte unterscheiden. Dadurch kann der Compiler unterscheiden, welche Version verwendet werden muss, wenn der Code die Eigenschaft oder Prozedur aufruft.

- **Nicht zulässige Unterschiede.** Das Ändern von mindestens einem der folgenden Punkte ist für das Überladen einer Eigenschaft oder Prozedur nicht gültig, da sie kein Bestandteil der Signatur sind:

  - ob ein Wert (für eine Prozedur) zurückgegeben wird

  - der Datentyp des Rückgabewerts (mit Ausnahme eines Konvertierungsoperators)

  - die Namen der Parameter oder Typparameter

  - die Einschränkungen hinsichtlich der Typparameter (für eine generische Prozedur)

  - Parametermodifiziererschlüsselwörter (wie `ByRef` oder `Optional`)

  - Eigenschaft oder Prozedurmodifiziererschlüsselwörter (wie `Public` oder `Shared`)

- **Optionaler Modifizierer.** Sie müssen den- `Overloads` Modifizierer nicht verwenden, wenn Sie mehrere überladene Eigenschaften oder Prozeduren in derselben Klasse definieren. Wenn Sie jedoch `Overloads` in einer der Deklarationen verwenden, müssen Sie sie in allen davon verwenden.

- **Shadoading und überladen.** `Overloads`kann auch verwendet werden, um ein vorhandenes Element oder einen Satz überladener Member in einer Basisklasse zu überschatten. Wenn Sie `Overloads` auf diese Art und Weise verwenden, deklarieren Sie die Eigenschaft oder Methode mit demselben Namen und derselben Parameterliste als Basisklassenmember, und Sie stellen das `Shadows`-Schlüsselwort nicht bereit.

Beim Verwenden von `Overrides` fügt der Compiler implizit `Overloads` hinzu, sodass Ihre Bibliotheks-APIs leichter mit C# verwendet werden können.

Der `Overloads`-Modifizierer kann in folgenden Kontexten verwendet werden:

- [Function-Anweisung](../statements/function-statement.md)

- [Operator Statement](../statements/operator-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Sub-Anweisung](../statements/sub-statement.md)

## <a name="see-also"></a>Weitere Informationen

- [Shadows](shadows.md)
- [Prozedurüberladung](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [Generische Typen in Visual Basic (Visual Basic)](../../programming-guide/language-features/data-types/generic-types.md)
- [Operatorprozeduren](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
