---
title: Die Delegatklasse "<classname>" hat keine Invoke-Methode. Ein Ausdruck dieses Typs kann daher nicht das Ziel eines Methodenaufrufs sein.
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 8339d038f845b8568f31f3068a98ccccf580aeae
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286649"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>Delegatklasse\<Klassenname >' hat keine Invoke-Methode, sodass ein Ausdruck dieses Typs kann nicht das Ziel eines Methodenaufrufs
Ein Aufruf von `Invoke` über einen Delegaten ist fehlgeschlagen, da `Invoke` ist nicht auf die Delegate-Klasse implementiert.  
  
 **Fehler-ID:** BC30220  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass mit eine Instanz von der "Delegate"-Klasse erstellt wurde eine `Dim` -Anweisung und die Delegatinstanz mit eine Prozedur zugewiesen wurde die `AddressOf` Operator.  
  
2.  Suchen Sie den Code, der die Delegate-Klasse implementiert, und stellen Sie sicher, dass es implementiert die `Invoke` Verfahren.  
  
## <a name="see-also"></a>Siehe auch
- [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)
