---
title: Der Custom-Modifizierer ist nicht gültig für Ereignisse, die ohne expliziten Delegattyp deklariert wurden.
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: c1b57ccdaa9e04c837ecf7572bc164683a934b2d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273516"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>Der Custom-Modifizierer ist nicht gültig für Ereignisse, die ohne expliziten Delegattyp deklariert wurden.
Im Gegensatz zu einem nicht-Custom-Ereignis eine `Custom Event` erfordert, dass ein `As` hinter den Ereignisnamen, die explizit den Typ des Delegaten für das Ereignis angibt.  
  
 Nicht benutzerdefinierte Ereignisse können werden entweder mit einer `As` -Klausel einen expliziten Delegattyp und mit einem Parameter Liste sofort nach dem Ereignisnamen.  
  
 **Fehler-ID:** BC31122  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Definieren Sie einen Delegaten mit derselben Parameterliste als das benutzerdefinierte Ereignis.  
  
     Z. B. wenn die `Custom Event` definiert wurde `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, und klicken Sie dann der entsprechende Delegaten würde folgendermaßen lauten.  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  Ersetzen Sie die Parameterliste des benutzerdefinierten Ereignisses mit einem `As` -Klausel, die den Delegattyp angibt.  
  
     Im Beispiel, `Custom Event` Deklaration würde wie folgt umgeschrieben werden.  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert eine `Custom Event` und die erforderliche `As` -Klausel mit einen Delegattyp aufweisen.  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)
- [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
