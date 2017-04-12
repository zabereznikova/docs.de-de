---
title: "Der Custom-Modifizierer ist nicht gültig für Ereignisse, die ohne expliziten Delegattyp deklariert | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31122
- bc31122
dev_langs:
- VB
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0e70fca6a0608df5db43156f70196b4e5c9b2339
ms.lasthandoff: 03/13/2017

---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>Der Custom-Modifizierer ist nicht gültig für Ereignisse, die ohne expliziten Delegattyp deklariert
Im Gegensatz zu einem Ereignis nicht benutzerdefiniert eine `Custom Event` Deklaration erfordert eine `As` -Klausel nach dem Ereignisnamen, die Typ des Delegaten für das Ereignis explizit angibt.  
  
 Nicht benutzerdefinierte Ereignisse kann entweder mit einem `As` -Klausel und einem expliziten Delegattyp oder mit einem Parameter Liste sofort nach dem Ereignisnamen.  
  
 **Fehler-ID:** BC31122  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Definieren Sie einen Delegaten mit einer Parameterliste, wie das benutzerdefinierte Ereignis.  
  
     Zum Beispiel wenn die `Custom Event` definiert wurde `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, und klicken Sie dann der entsprechende Delegaten würde folgendermaßen lauten.  
  
     [!code-vb[VbVbalrEventError&18;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  Ersetzen Sie die Parameterliste des benutzerdefinierten Ereignisses durch eine `As` -Klausel, die dem Typ des Delegaten angibt.  
  
     Ausgehend vom Beispiel `Custom Event` Deklaration wie folgt umgeschrieben.  
  
     [!code-vb[VbVbalrEventError Nr.&19;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel deklariert eine `Custom Event` und die erforderliche `As` -Klausel mit einem Delegattyp angegeben.  
  
 [!code-vb[VbVbalrEventError&#2;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
