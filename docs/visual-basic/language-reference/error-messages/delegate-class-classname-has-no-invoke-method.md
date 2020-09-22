---
title: Die Delegatklasse "<classname>" hat keine Invoke-Methode. Ein Ausdruck dieses Typs kann daher nicht das Ziel eines Methodenaufrufs sein.
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: e6ad06262806088347c94b3040b743618a3b3695
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874502"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>Die Delegatklasse "\<classname>" hat keine Invoke-Methode. Ein Ausdruck dieses Typs kann daher nicht das Ziel eines Methodenaufrufs sein.

Ein Aufruf von `Invoke` über einen Delegaten ist fehlgeschlagen, da `Invoke` nicht in der Delegatklasse implementiert ist.  
  
 **Fehler-ID:** BC30220  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie sicher, dass eine Instanz der Delegatklasse mit einer `Dim` -Anweisung erstellt wurde und dass der Delegatinstanz mit dem-Operator eine Prozedur zugewiesen wurde `AddressOf` .  
  
2. Suchen Sie den Code, der die Delegatklasse implementiert, und stellen Sie sicher, dass Sie die `Invoke` Prozedur implementiert.  
  
## <a name="see-also"></a>Weitere Informationen

- [Delegaten](../../programming-guide/language-features/delegates/index.md)
- [Delegate-Anweisung](../statements/delegate-statement.md)
- [AddressOf-Operator](../operators/addressof-operator.md)
- [Dim-Anweisung](../statements/dim-statement.md)
