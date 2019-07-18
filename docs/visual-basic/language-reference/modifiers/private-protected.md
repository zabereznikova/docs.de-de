---
title: Privat geschützt (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: fea43558ac0fe8181f2786b69f2621346d446b2e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920496"
---
# <a name="private-protected-visual-basic"></a>Privat geschützt (Visual Basic)

Die Schlüsselwortkombination `Private Protected` ist ein Zugriffsmodifizierer für Member. Ein `Private Protected` angehört, zugegriffen werden kann, indem Sie alle Elemente in der enthaltenden Klasse sowie Typen, die von der enthaltenden Klasse abgeleitet, jedoch nur, wenn sie in der enthaltenden Assembly gefunden werden.

Sie können angeben, `Private Protected` nur auf Member von Klassen; Sie können nicht angewendet werden `Private Protected` zu Membern einer Struktur da Strukturen nicht geerbt werden können.

Die `Private Protected` Zugriffsmodifizierer wird von Visual Basic 15.5 und höher unterstützt. Sie können das folgende Element auf Visual Basic-Projekt hinzufügen, um es zu verwenden (\*.vbproj) Datei. Solange Visual Basic 15.5 oder höher auf Ihrem System installiert ist, können dass Sie alle der Features von Programmiersprachen unterstützt werden, indem Sie die neueste Version von Visual Basic-Compiler nutzen:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Weitere Informationen finden Sie unter [Festlegen der Sprache Visual Basic-Version](../../language-reference/configure-language-version.md).

> [!NOTE]
> Wählen Sie in Visual Studio F1-Hilfe auf `private protected` enthält die Hilfe für entweder [private](private.md) oder [geschützt](protected.md). Die IDE wählt die einzelne Token unter dem Cursor anstatt der zusammengesetzte Begriff.

## <a name="rules"></a>Regeln

- **Deklarationskontext.** Sie können `Private Protected` nur auf Klassenebene. Dies bedeutet, dass der Deklarationskontext für eine `Protected` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich.

## <a name="behavior"></a>Verhalten

- **Zugriffsebene.** Gesamten Code in einer Klasse kann Zugriff auf die Elemente auf. Code in einer Klasse, die von einer Basisklasse abgeleitet wird und in derselben Assembly enthalten ist, kann auf alle zugreifen der `Private Protected` Elemente der Basisklasse. Jedoch nicht im Code jeder Klasse, die von einer Basisklasse abgeleitet wird und in einer anderen Assembly enthalten ist die Basisklasse der Klasse zugreifen `Private Protected` Elemente.

- **Zugriffsmodifizierer.** Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*. Einen Vergleich der Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

Der `Private Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:

- [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md) einer geschachtelten Klasse

- [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)

- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) eines Delegaten, die in einer Klasse geschachtelt sind

- [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)

- [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md) einer Enumeration, die in einer Klasse geschachtelt sind

- [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)

- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)

- [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md) einer Schnittstelle, die in einer Klasse geschachtelt sind

- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)

- [Strukturieren Sie die Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md) einer Struktur geschachtelt werden, in einer Klasse

- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>Siehe auch

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Protected Friend](./protected-friend.md)
- [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
