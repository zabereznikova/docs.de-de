---
title: Eine Anweisung kann keinen Block außerhalb einer "If"-Zeilenanweisung beenden.
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 4fd7577accd0b312ee1e3d2d990d256514d5f5f6
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161334"
---
# <a name="bc32005-statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>BC32005: die Anweisung kann keinen Block außerhalb einer "if"-Zeilen Anweisung beenden.

Eine einzeilige `If` Anweisung enthält mehrere durch Doppelpunkte getrennte Anweisungen (:), von denen eine eine- `End` Anweisung für einen Kontroll Block außerhalb der einzeiligen ist `If` . Einzeilige `If` Anweisungen verwenden nicht die- `End If` Anweisung.

 **Fehler-ID:** BC32005

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Verschieben Sie die einzeilige `If` Anweisung außerhalb des Kontroll Blocks, der die- `End If` Anweisung enthält.

## <a name="see-also"></a>Siehe auch

- [If...Then...Else-Anweisung](../statements/if-then-else-statement.md)
