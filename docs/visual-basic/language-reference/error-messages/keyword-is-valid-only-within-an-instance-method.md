---
title: <keyword> ist nur innerhalb einer Instanzenmethode gültig.
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: ad39ade294b362b20f2dfb93455445bf41d056cd
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163323"
---
# <a name="bc30043-keyword-is-valid-only-within-an-instance-method"></a>BC30043: " \<keyword> " ist nur innerhalb einer Instanzmethode gültig

Die `Me` `MyClass` `MyBase` Schlüsselwörter, und verweisen auf bestimmte Klassen Instanzen. Sie können Sie nicht in einer freigegebenen- `Function` oder- `Sub` Prozedur verwenden.

*Fehler-ID:** BC30043

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Entfernen Sie das-Schlüsselwort aus der Prozedur, oder entfernen Sie das- `Shared` Schlüsselwort aus der Prozedur Deklaration.

## <a name="see-also"></a>Siehe auch

- [Zuweisung von Objektvariablen](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase und MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Grundlagen der Vererbung](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
