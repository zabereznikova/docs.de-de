---
title: Vorangestellte "." oder "!" können nur in einer With-Anweisung verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 4ff273d5930fe58a5bccf0f4f4c10e971d777d01
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162504"
---
# <a name="bc30157-leading--or--can-only-appear-inside-a-with-statement"></a>BC30157: die führende "." oder "!" können nur in einer with-Anweisung angezeigt werden.

Ein Punkt (.) oder ein Ausrufezeichen (!), das sich nicht in einem-Block befindet, `With` tritt ohne einen Ausdruck auf der linken Seite auf. Member Access ( `.` ) und Dictionary Member Access ( `!` ) erfordern einen Ausdruck, der das Element angibt, das den Member enthält. Dieser muss direkt links neben dem-Accessor oder als Ziel eines Blocks angezeigt werden, der `With` den Member-Zugriff enthält.

 **Fehler-ID:** BC30157

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Stellen Sie sicher, dass der `With` Block korrekt formatiert ist.

2. Wenn kein-Block vorhanden ist `With` , fügen Sie links neben dem Accessor einen Ausdruck hinzu, der zu einem definierten Element ausgewertet wird, das den Member enthält.

## <a name="see-also"></a>Siehe auch

- [Sonderzeichen in Code](../../programming-guide/program-structure/special-characters-in-code.md)
- [With...End With-Anweisung](../statements/with-end-with-statement.md)
