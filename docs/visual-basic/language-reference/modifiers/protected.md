---
title: Geschützt
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: 740c998b8a6ccc6798bce37e9b08e408dac7c17d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351304"
---
# <a name="protected-visual-basic"></a>Protected (Visual Basic)

Ein Member-Zugriffsmodifizierer, der angibt, dass auf ein oder mehrere deklarierte Programmier Elemente nur aus ihrer eigenen Klasse oder aus einer abgeleiteten Klasse zugegriffen werden kann.

## <a name="remarks"></a>Hinweise

Manchmal enthält ein in einer Klasse deklariertes Programmier Element sensible Daten oder eingeschränkten Code, und Sie möchten den Zugriff auf das Element einschränken. Wenn die Klasse jedoch vererbbar ist und Sie eine Hierarchie abgeleiteter Klassen erwarten, kann es erforderlich sein, dass diese abgeleiteten Klassen auf die Daten oder den Code zugreifen. In einem solchen Fall soll der Zugriff auf das Element sowohl von der Basisklasse als auch von allen abgeleiteten Klassen erfolgen. Um den Zugriff auf ein Element auf diese Weise einzuschränken, können Sie es mit `Protected`deklarieren.

> [!NOTE]
> Der `Protected` Zugriffsmodifizierer kann mit zwei anderen Modifizierern kombiniert werden:
>
> - Der [Protected Friend](protected-friend.md) -Modifizierer macht einen Klassenmember aus dieser Klasse, aus abgeleiteten Klassen und aus derselben Assembly, in der die Klasse definiert ist, zugänglich.
> - Der [private geschützte](private-protected.md) Modifizierer macht einen Klassenmember für abgeleitete Typen zugänglich, aber nur innerhalb der enthaltenden Assembly.

## <a name="rules"></a>Regeln

**Deklarations Kontext.** Sie können `Protected` nur auf Klassenebene verwenden. Dies bedeutet, dass der Deklarations Kontext für ein `Protected` Element eine Klasse sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur sein darf.

## <a name="behavior"></a>Verhalten

- **Zugriffsebene.** Der gesamte Code in einer Klasse kann auf seine Elemente zugreifen. Code in jeder Klasse, die von einer Basisklasse abgeleitet wird, kann auf alle `Protected` Elemente der Basisklasse zugreifen. Dies gilt für alle Generations Generierungen. Dies bedeutet, dass eine Klasse auf `Protected` Elemente der Basisklasse der Basisklasse usw. zugreifen kann.

     Geschützter Zugriff ist keine übergeordnete Gruppe oder eine Teilmenge des Friend-Zugriffs.

- **Zugriffsmodifizierer** Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet. Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

Der `Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:

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

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
