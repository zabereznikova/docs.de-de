---
title: Die Delegatklasse "<classname>" hat keine Invoke-Methode. Ein Ausdruck dieses Typs kann daher nicht das Ziel eines Methodenaufrufs sein.
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 4e0fc61c7356008755134f670fa1fab0165cfd48
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162790"
---
# <a name="bc30220-delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>BC30220: die Delegatklasse " \<classname> " hat keine Aufruf Methode. ein Ausdruck dieses Typs kann daher nicht das Ziel eines Methoden Aufrufs sein.

Ein Aufruf von `Invoke` über einen Delegaten ist fehlgeschlagen, da `Invoke` nicht in der Delegatklasse implementiert ist.

 **Fehler-ID:** BC30220

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Stellen Sie sicher, dass eine Instanz der Delegatklasse mit einer `Dim` -Anweisung erstellt wurde und dass der Delegatinstanz mit dem-Operator eine Prozedur zugewiesen wurde `AddressOf` .

2. Suchen Sie den Code, der die Delegatklasse implementiert, und stellen Sie sicher, dass Sie die `Invoke` Prozedur implementiert.

## <a name="see-also"></a>Siehe auch

- [Delegaten](../../programming-guide/language-features/delegates/index.md)
- [Delegate-Anweisung](../statements/delegate-statement.md)
- [AddressOf-Operator](../operators/addressof-operator.md)
- [Dim-Anweisung](../statements/dim-statement.md)
