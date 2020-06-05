---
title: Protected
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
ms.openlocfilehash: d66ed68004f8b6ef21ae703f02b317589814764b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398219"
---
# <a name="protected-visual-basic"></a>Protected (Visual Basic)

Ein Member-Zugriffsmodifizierer, der angibt, dass auf ein oder mehrere deklarierte Programmier Elemente nur aus ihrer eigenen Klasse oder aus einer abgeleiteten Klasse zugegriffen werden kann.

## <a name="remarks"></a>Bemerkungen

Manchmal enthält ein in einer Klasse deklariertes Programmier Element sensible Daten oder eingeschränkten Code, und Sie möchten den Zugriff auf das Element einschränken. Wenn die Klasse jedoch vererbbar ist und Sie eine Hierarchie abgeleiteter Klassen erwarten, kann es erforderlich sein, dass diese abgeleiteten Klassen auf die Daten oder den Code zugreifen. In einem solchen Fall soll der Zugriff auf das Element sowohl von der Basisklasse als auch von allen abgeleiteten Klassen erfolgen. Um den Zugriff auf ein Element auf diese Weise einzuschränken, können Sie es mit deklarieren `Protected` .

> [!NOTE]
> Der `Protected` Zugriffsmodifizierer kann mit zwei anderen Modifizierern kombiniert werden:
>
> - Der [Protected Friend](protected-friend.md) -Modifizierer macht einen Klassenmember aus dieser Klasse, aus abgeleiteten Klassen und aus derselben Assembly, in der die Klasse definiert ist, zugänglich.
> - Der [private geschützte](private-protected.md) Modifizierer macht einen Klassenmember für abgeleitete Typen zugänglich, aber nur innerhalb der enthaltenden Assembly.

## <a name="rules"></a>Regeln

**Deklarationskontext.** Sie können `Protected` nur auf Klassenebene verwenden. Dies bedeutet, dass der Deklarations Kontext für ein `Protected` -Element eine-Klasse sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur sein darf.

## <a name="behavior"></a>Verhalten

- **Zugriffsebene.** Der gesamte Code in einer Klasse kann auf seine Elemente zugreifen. Code in jeder Klasse, die von einer Basisklasse abgeleitet wird, kann auf alle `Protected` Elemente der Basisklasse zugreifen. Dies gilt für alle Generations Generierungen. Dies bedeutet, dass eine Klasse `Protected` auf Elemente der Basisklasse der Basisklasse zugreifen kann usw.

     Geschützter Zugriff ist keine übergeordnete Gruppe oder eine Teilmenge des Friend-Zugriffs.

- **Zugriffsmodifizierer** Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet. Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

Der `Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:

- [Class-Anweisung](../statements/class-statement.md)

- [Const-Anweisung](../statements/const-statement.md)

- [Declare Statement](../statements/declare-statement.md)

- [Delegate-Anweisung](../statements/delegate-statement.md)

- [Dim-Anweisung](../statements/dim-statement.md)

- [Enum-Anweisung](../statements/enum-statement.md)

- [Event-Anweisung](../statements/event-statement.md)

- [Function-Anweisung](../statements/function-statement.md)

- [Interface-Anweisung](../statements/interface-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Structure Statement](../statements/structure-statement.md)

- [Sub-Anweisung](../statements/sub-statement.md)

## <a name="see-also"></a>Weitere Informationen

- [Öffentlich](public.md)
- [Kollegen](friend.md)
- [Privat](private.md)
- [Privat geschützt](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Vorgehensweisen](../../programming-guide/language-features/procedures/index.md)
- [Strukturen](../../programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../programming-guide/language-features/objects-and-classes/index.md)
