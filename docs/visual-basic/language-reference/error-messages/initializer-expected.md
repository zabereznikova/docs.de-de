---
title: Initialisierer erwartet
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: cbe77bab3e4f8bf2094c70c1c16d95ee897c729e
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163011"
---
# <a name="bc30996-initializer-expected"></a>BC30996: Initialisierer erwartet

Sie haben versucht, eine Instanz einer Klasse zu deklarieren, indem Sie einen Objektinitialisierer verwenden, in dem die Initialisierungs Liste leer ist, wie im folgenden Beispiel gezeigt.

 `' Not valid.`

 `' Dim aStudent As New Student With {}`

 Mindestens ein Feld oder eine Eigenschaft muss in der Initialisiererliste initialisiert werden, wie im folgenden Beispiel gezeigt.

 `Dim aStudent As New Student With {.year = "Senior"}`

 **Fehler-ID:** BC30996

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Initialisieren Sie mindestens ein Feld oder eine Eigenschaft im Initialisierer, oder verwenden Sie keinen Objektinitialisierer.

## <a name="see-also"></a>Siehe auch

- [Objektinitialisierer: benannte und anonyme Typen](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
