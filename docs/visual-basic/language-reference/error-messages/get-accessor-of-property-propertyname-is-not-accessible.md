---
title: Auf den Get-Accessor der <propertyname>-Eigenschaft kann nicht zugegriffen werden.
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: 8fb78f3c14708c79f1910e202287c25a3b2213b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803050"
---
# <a name="get-accessor-of-property-propertyname-is-not-accessible"></a>"Get-Accessor der Eigenschaft"\<Propertyname >' kann nicht zugegriffen werden
Eine Anweisung versucht, den Wert einer Eigenschaft abzurufen, wenn sie den Zugriff auf die Eigenschaft keinen `Get` Verfahren.  
  
 Wenn die [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) mit einem restriktiveren Zugriffsebene als markiert ist seine [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), beim Lesen des Eigenschaftswerts kann fehlschlagen, in den folgenden Fällen:  
  
- Die `Get` Anweisung RuntimeCompatibility [Private](../../../visual-basic/language-reference/modifiers/private.md) und der aufrufende Code ist außerhalb der Klasse oder Struktur, in dem die Eigenschaft definiert ist.  
  
- Die `Get` Anweisung RuntimeCompatibility [geschützte](../../../visual-basic/language-reference/modifiers/protected.md) und der aufrufende Code ist nicht in der Klasse oder Struktur, die in der die Eigenschaft definiert ist, noch in einer abgeleiteten Klasse.  
  
- Die `Get` Anweisung RuntimeCompatibility [Friend](../../../visual-basic/language-reference/modifiers/friend.md) und der aufrufende Code ist nicht in der gleichen Assembly, in dem die Eigenschaft definiert wird.  
  
 **Fehler-ID:** BC31103  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenn Sie die Kontrolle über den Quellcode, der die Eigenschaft haben, sollten Sie deklarieren die `Get` Prozedur mit die gleiche Zugriffsebene wie die Eigenschaft selbst.  
  
- Wenn Sie keine Kontrolle über den Quellcode, der die Eigenschaft definieren, oder Sie einschränken, müssen die `Get` Prozedur Zugriffsebene mehr als die Eigenschaft selbst, versuchen Sie es, um die Anweisung zu verschieben, die Wert der Eigenschaft, um einen Codebereich liest, die besseren Zugriff auf die Diese Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch

- [Eigenschaftenprozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
