---
title: Shadows (Visual Basic)
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
ms.openlocfilehash: c9dfff99e2634b79ad6b44721f40583d21c9b98e
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67664131"
---
# <a name="shadows-visual-basic"></a>Shadows (Visual Basic)

Gibt an, dass ein deklariertes Programmierelement ein Element Blendet eine mit dem gleichen Namen oder einen Satz überladener Elemente in einer Basisklasse erneut deklariert.

## <a name="remarks"></a>Hinweise

Der Hauptzweck des shadowings (Dies ist auch bekannt als *Ausblenden von Namen*) besteht darin, die Definition von Klassenmembern beizubehalten. Die Basisklasse kann eine Änderung durchlaufen, die ein Element mit dem gleichen Namen wie eine erstellt wird, die Sie bereits definiert haben. In diesem Fall die `Shadows` Modifizierer erzwingt, dass Verweise über die Klasse, um der Member aufgelöst werden Sie definiert, statt auf das neue Element der Basisklasse.

Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen. Weitere Informationen finden Sie unter [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).

## <a name="rules"></a>Regeln

- **Deklarationskontext.** Sie können `Shadows` nur auf Klassenebene. Dies bedeutet, dass der Deklarationskontext für eine `Shadows` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich.

  Sie können nur ein shadowing-Element in einer einzigen deklarationsanweisung deklarieren.

- **Kombinierte Modifizierer.** Sie können keine angeben `Shadows` zusammen mit `Overloads`, `Overrides`, oder `Static` in der gleichen Deklaration.

- **Elementtypen.** Sie können ein Shadowing von jedem deklarierten Element mit einer anderen Art vornehmen. Wenn Sie Shadowing für eine Eigenschaft oder Prozedur mit einer anderen Eigenschaft oder Prozedur, müssen die Parameter sowie des Rückgabetyps nicht mit denen in der Basisklasse-Eigenschaft oder Prozedur übereinstimmen.

- **Zugriff auf.** Das Shadowing-Element in der Basisklasse ist normalerweise nicht verfügbar, in der abgeleiteten Klasse, die es Shadowing durchführt. Allerdings gelten die folgenden Überlegungen.

  - Ist das shadowing-Element nicht zugegriffen werden kann, aus dem Code, der darauf verweist, wird der Verweis auf das Shadowing-Element aufgelöst. Z. B. wenn ein `Private` Element führt Shadowing für eine Basisklasse-Element, Code, der keine Berechtigung zum Zugriff auf die `Private` Element greift stattdessen auf das Basisklasse-Element.

  - Wenn Sie ein Element spiegeln, können Sie weiterhin das Shadowing-Element durch ein Objekt mit dem Typ der Basisklasse deklariert zugreifen. Sie können auch über zugreifen `MyBase`.

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
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
