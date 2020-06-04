---
title: Die Delegatklasse "<classname>" hat keine Invoke-Methode. Ein Ausdruck dieses Typs kann daher nicht das Ziel eines Methodenaufrufs sein.
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 27be97ba2930791bcb9012c824bc418a0089b037
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409711"
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
