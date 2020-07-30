---
title: Protected Friend
ms.date: 05/10/2018
f1_keywords:
- vb.ProtectedFriend
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 27fc993ca0b94d406261d5e6275de8cd619eb6a8
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303451"
---
# <a name="protected-friend-visual-basic"></a>Geschützter Freund (Visual Basic)

Die Schlüsselwortkombination `Protected Friend` ist ein Zugriffsmodifizierer für Member. Sie überträgt sowohl [Friend](friend.md) -als auch [geschützten](protected.md) Zugriff auf die deklarierten Elemente, sodass Sie von überall in derselben Assembly, von ihrer eigenen Klasse und von abgeleiteten Klassen aus darauf zugreifen können. Sie können `Protected Friend` nur für Member von Klassen angeben. Sie können nicht auf Member einer Struktur anwenden, `Protected Friend` da Strukturen nicht vererbt werden können.

> [!NOTE]
> Wenn Sie in Visual Studio die F1-Hilfe in auswählen, erhalten Sie `protected friend` Hilfe für den [geschützten](protected.md) oder einen [Friend](friend.md)-. Die IDE wählt anstelle des Verbund Worts das einzelne Token unter dem Cursor aus.

## <a name="rules"></a>Regeln

**Deklarationskontext.** Sie können `Protected Friend` nur auf Klassenebene verwenden. Dies bedeutet, dass der Deklarations Kontext für ein `Protected` -Element eine-Klasse sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur sein darf.

## <a name="see-also"></a>Siehe auch

- [Öffentlich](public.md)
- [Gebieten](protected.md)
- [Kollegen](friend.md)
- [Privat](private.md)
- [Privat geschützt](./private-protected.md)
- [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Vorgehensweisen](../../programming-guide/language-features/procedures/index.md)
- [Strukturen](../../programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../programming-guide/language-features/objects-and-classes/index.md)
