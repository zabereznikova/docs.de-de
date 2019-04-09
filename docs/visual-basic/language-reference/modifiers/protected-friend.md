---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 331c63dc290d4096e8158f265ee869b47743a273
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151774"
---
# <a name="protected-friend-visual-basic"></a>Protected Friend (Visual Basic)

Die Schlüsselwortkombination `Protected Friend` ist ein Zugriffsmodifizierer für Member. Es bietet sowohl [Friend](friend.md) Zugriff und [geschützte](protected.md) der deklarierten Elemente, damit sie über eine beliebige Stelle in der gleichen Assembly, von ihrer eigenen Klasse und von abgeleiteten Klassen zugänglich sind. Sie können angeben, `Protected Friend` nur auf Member von Klassen; Sie können nicht angewendet werden `Protected Friend` zu Membern einer Struktur da Strukturen nicht geerbt werden können.

> [!NOTE]
> Wählen Sie in Visual Studio F1-Hilfe auf `protected friend` enthält die Hilfe für entweder [geschützt](protected.md) oder [Friend](friend.md). Die IDE wählt die einzelne Token unter dem Cursor anstatt der zusammengesetzte Begriff.

## <a name="rules"></a>Regeln

- **Deklarationskontext.** Sie können `Protected Friend` nur auf Klassenebene. Dies bedeutet, dass der Deklarationskontext für eine `Protected` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich. 

## <a name="see-also"></a>Siehe auch

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Privat geschützt](./private-protected.md)
- [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
