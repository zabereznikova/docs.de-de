---
title: '&#39;Benutzerdefinierte&#39; Modifizierer ist nicht gültig für Ereignisse, die ohne expliziten Delegattyp deklariert werden.'
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 3f08bbbbbac4a01dfbac8d15cf9285c01262618a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>&#39;Benutzerdefinierte&#39; Modifizierer ist nicht gültig für Ereignisse, die ohne expliziten Delegattyp deklariert werden.
Im Gegensatz zu einem Ereignis nicht benutzerdefinierte eine `Custom Event` Deklaration erfordert eine `As` -Klausel nach dem Ereignisnamen, die explizit den Typ des Delegaten für das Ereignis angibt.  
  
 Nicht benutzerdefinierte Ereignisse kann entweder mit einem `As` -Klausel und einem expliziten Delegattyp oder mit einem Parameter Liste sofort nach dem Ereignisnamen.  
  
 **Fehler-ID:** BC31122  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Definieren Sie einen Delegaten mit derselben Parameterliste, wie das benutzerdefinierte Ereignis.  
  
     Z. B. wenn die `Custom Event` wurde definiert, mit `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, und klicken Sie dann der entsprechende Delegaten Folgendes wäre.  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  Ersetzen Sie die Parameterliste des benutzerdefinierten Ereignisses mit einem `As` -Klausel, die den Typ des Delegaten angibt.  
  
     Fahren Sie mit dem Beispiel `Custom Event` Deklaration würde wie folgt umgeschrieben werden.  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel deklariert eine `Custom Event` und gibt die erforderliche `As` -Klausel mit einem Delegattyp als Typ.  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
