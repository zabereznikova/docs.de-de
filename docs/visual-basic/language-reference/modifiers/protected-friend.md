---
title: Protected Friend
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: f92021f5f0dab9762470c270bdd5182187d587e5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351324"
---
# <a name="protected-friend-visual-basic"></a>Geschützter Freund (Visual Basic)

Die Schlüsselwortkombination `Protected Friend` ist ein Zugriffsmodifizierer für Member. Sie überträgt sowohl [Friend](friend.md) -als auch [geschützten](protected.md) Zugriff auf die deklarierten Elemente, sodass Sie von überall in derselben Assembly, von ihrer eigenen Klasse und von abgeleiteten Klassen aus darauf zugreifen können. Sie können `Protected Friend` nur für Member von Klassen angeben. Sie können `Protected Friend` nicht auf Member einer Struktur anwenden, da Strukturen nicht vererbt werden können.

> [!NOTE]
> Wenn Sie in Visual Studio die F1-Hilfe auf `protected friend` auswählen, finden Sie Hilfe für den [geschützten](protected.md) oder den [Friend](friend.md)-. Die IDE wählt anstelle des Verbund Worts das einzelne Token unter dem Cursor aus.

## <a name="rules"></a>Regeln

**Deklarations Kontext.** Sie können `Protected Friend` nur auf Klassenebene verwenden. Dies bedeutet, dass der Deklarations Kontext für ein `Protected` Element eine Klasse sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur sein darf.

## <a name="see-also"></a>Siehe auch

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](./private-protected.md)
- [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
