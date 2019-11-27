---
title: Shadows
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: e9a423fa69ad1dcd8c1d4a5b7085e5b5da548f93
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351264"
---
# <a name="shadows-visual-basic"></a>Shadows (Visual Basic)

Gibt an, dass ein deklariertes Programmier Element ein identisch benanntes Element oder einen Satz überladener Elemente in einer Basisklasse erneut deklariert und verbirgt.

## <a name="remarks"></a>Hinweise

Der Hauptzweck von Shadowing(das auch als ausblenden *nach Name*bezeichnet wird) besteht darin, die Definition der Klassenmember beizubehalten. Die Basisklasse kann einer Änderung unterzogen werden, die ein Element mit dem gleichen Namen erstellt, den Sie bereits definiert haben. In diesem Fall erzwingt der `Shadows` Modifizierer, dass Verweise durch Ihre Klasse in den von Ihnen definierten Member aufgelöst werden, anstatt das neue Basisklassen Element zu verwenden.

Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen. Weitere Informationen finden Sie unter [shadowingin Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).

## <a name="rules"></a>Regeln

- **Deklarations Kontext.** Sie können `Shadows` nur auf Klassenebene verwenden. Dies bedeutet, dass der Deklarations Kontext für ein `Shadows` Element eine Klasse sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur sein darf.

  Sie können nur ein Shadowingelement in einer einzelnen Deklarations Anweisung deklarieren.

- **Kombinierte modifiziererer.** Sie können `Shadows` nicht mit `Overloads`, `Overrides`oder `Static` in derselben Deklaration angeben.

- **Element Typen.** Sie können ein Shadowing von jedem deklarierten Element mit einer anderen Art vornehmen. Wenn Sie eine Eigenschaft oder Prozedur mit einer anderen Eigenschaft oder Prozedur überschatten, müssen die Parameter und der Rückgabetyp nicht mit denen in der Basisklassen Eigenschaft oder-Prozedur identisch sein.

- **Den.** Das Shadowing-Element in der Basisklasse ist normalerweise nicht in der abgeleiteten Klasse verfügbar, die es Shadowing durchführt. Es gelten jedoch die folgenden Überlegungen.

  - Wenn auf das Shadowing-Element nicht über den Code zugegriffen werden kann, auf das verwiesen wird, wird der Verweis in das Shadowing-Element aufgelöst. Wenn z. b. ein `Private` Element ein Basisklassen Element Shadowing, greift Code, der nicht über die Berechtigung für den Zugriff auf das `Private` Element verfügt, stattdessen auf das Basisklassen Element zu.

  - Wenn Sie einen Schatten für ein Element durchlaufen, können Sie weiterhin auf das Shadowing Element über ein Objekt zugreifen, das mit dem Typ der Basisklasse deklariert wurde. Sie können auch über `MyBase`darauf zugreifen.

Der `Shadows`-Modifizierer kann in folgenden Kontexten verwendet werden:

- [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)

- [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)

- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)

- [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md)

- [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)

- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)

- [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)

- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)

- [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)

- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>Siehe auch

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Static](../../../visual-basic/language-reference/modifiers/static.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Me, My, MyBase und MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Shadodown in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
