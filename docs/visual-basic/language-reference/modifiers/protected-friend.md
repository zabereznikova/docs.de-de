---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: b72cbee0394043620e792d1c014bfe55121e175e
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/18/2018
ms.locfileid: "34306541"
---
# <a name="protected-friend-visual-basic"></a>Protected Friend (Visual Basic)

Die Schlüsselwortkombination `Protected Friend` ist ein Zugriffsmodifizierer für Member. Er überträgt sowohl ["Friend"](friend.md) Zugriff und [geschützte](protected.md) Zugriff auf deklarierte Elemente, sodass sie über eine beliebige Stelle in der gleichen Assembly, von ihrer eigenen Klasse und von abgeleiteten Klassen zugänglich sind. Sie können angeben, `Protected Friend` nur auf Member von Klassen; können nicht angewendet `Protected Friend` zu Membern einer Struktur da Strukturen können nicht vererbt werden.

> [!NOTE]
> Wählen Sie in Visual Studio F1-Hilfe auf `protected friend` enthält die Hilfe für entweder [geschützt](protected.md) oder ["Friend"](friend.md). Die IDE wählt der einzelnen Tokens, das unter den Cursor und nicht als zusammengesetztes Wort.

## <a name="rules"></a>Regeln

- **Deklarationskontext.** Sie können `Protected Friend` nur auf Klassenebene. Dies bedeutet, dass der Deklarationskontext für eine `Protected` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich. 


## <a name="see-also"></a>Siehe auch

[Public](../../../visual-basic/language-reference/modifiers/public.md)  
[Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
["Friend"](friend.md)   
[Private](../../../visual-basic/language-reference/modifiers/private.md)  
[Geschützt privat](./private-protected.md)   
[Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
