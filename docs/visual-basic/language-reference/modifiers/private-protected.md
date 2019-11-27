---
title: Private Protected
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 265141f77f4a61a61414a07214830feaa8a1ab05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351347"
---
# <a name="private-protected-visual-basic"></a>Privat geschützt (Visual Basic)

Die Schlüsselwortkombination `Private Protected` ist ein Zugriffsmodifizierer für Member. Auf einen `Private Protected` Member kann sowohl von allen Membern in der enthaltenden Klasse als auch von Typen, die von der enthaltenden Klasse abgeleitet sind, zugegriffen werden, jedoch nur, wenn Sie in der enthaltenden Assembly gefunden werden.

Sie können `Private Protected` nur für Member von Klassen angeben. Sie können `Private Protected` nicht auf Member einer Struktur anwenden, da Strukturen nicht vererbt werden können.

Der `Private Protected` Zugriffsmodifizierer wird von Visual Basic 15,5 und höher unterstützt. Um es zu verwenden, können Sie das folgende-Element der Visual Basic Project-Datei (\*. vbproj) hinzufügen. Solange Visual Basic 15,5 oder höher auf Ihrem System installiert ist, können Sie alle sprach Features nutzen, die von der neuesten Version des Visual Basic Compilers unterstützt werden:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Weitere Informationen finden Sie [unter Festlegen der Visual Basic Sprachversion](../../language-reference/configure-language-version.md).

> [!NOTE]
> Wenn Sie in Visual Studio die F1-Hilfe auf `private protected` auswählen, finden Sie Hilfe für [Privat](private.md) oder [geschützt](protected.md). Die IDE wählt anstelle des Verbund Worts das einzelne Token unter dem Cursor aus.

## <a name="rules"></a>Regeln

- **Deklarations Kontext.** Sie können `Private Protected` nur auf Klassenebene verwenden. Dies bedeutet, dass der Deklarations Kontext für ein `Protected` Element eine Klasse sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur sein darf.

## <a name="behavior"></a>Verhalten

- **Zugriffsebene.** Der gesamte Code in einer Klasse kann auf seine Elemente zugreifen. Code in jeder Klasse, die von einer Basisklasse abgeleitet ist und in derselben Assembly enthalten ist, kann auf alle `Private Protected` Elemente der Basisklasse zugreifen. Allerdings kann Code in einer beliebigen Klasse, die von einer Basisklasse abgeleitet ist und in einer anderen Assembly enthalten ist, nicht auf die `Private Protected` Elemente der Basisklasse zugreifen.

- **Zugriffsmodifizierer** Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet. Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

Der `Private Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:

- [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md) einer "netsted"-Klasse

- [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)

- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Delegatanweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) eines Delegaten, der in einer Klasse eingebettet ist

- [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)

- [Enumerationsanweisung](../../../visual-basic/language-reference/statements/enum-statement.md) einer Enumeration, die in einer Klasse eingefügt ist

- [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)

- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)

- [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md) einer Schnittstelle, die in einer Klasse eingebettet ist

- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)

- [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md) einer Struktur, die in einer Klasse eingebettet ist

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
