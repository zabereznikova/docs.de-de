---
title: Name &quot;&lt;Namen&gt;&quot; ist nicht deklariert | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
dev_langs:
- VB
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
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
ms.openlocfilehash: 81b6862a7f8ceb7998b2ea53336ed3af46b1db5f
ms.lasthandoff: 03/13/2017

---
# <a name="name-39ltnamegt39-is-not-declared"></a>Name '&lt;Namen&gt;' ist nicht deklariert.
Eine Anweisung verweist auf ein Programmierelement, aber der Compiler kann ein Element mit genau diesem Namen nicht finden.  
  
 **Fehler-ID:** BC30451  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die Schreibweise des Namens in der verweisenden Anweisung. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Groß-und Kleinschreibung, wird jedoch eine andere Veränderung der Schreibweise gilt als einen völlig anderen Namen. Beachten Sie, dass der Unterstrich (`_`) Teil des Namens und daher Teil der Schreibweise ist.  
  
2.  Überprüfen Sie, ob den Memberzugriffsoperator (`.`) zwischen einem Objekt und seine Member. Angenommen, Sie haben ein <xref:System.Windows.Forms.TextBox>-Steuerelement namens `TextBox1`, für den Zugriff auf die <xref:System.Windows.Forms.TextBoxBase.Text%2A>Eigenschaft Sie geben `TextBox1.Text`.</xref:System.Windows.Forms.TextBoxBase.Text%2A> </xref:System.Windows.Forms.TextBox> Wenn Sie stattdessen `TextBox1Text`eingeben, haben Sie einen anderen Namen erstellt.  
  
3.  Wenn die Schreibweise richtig ist, und die Syntax von jedem Objekt Memberzugriff richtig ist, stellen Sie sicher, dass das Element deklariert wurde. Weitere Informationen finden Sie unter [deklarierten Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).  
  
4.  Das Programmierelement deklariert wurde, überprüfen Sie, ob es im Gültigkeitsbereich befindet. Wenn die verweisende Anweisung außerhalb des Bereichs, der das Programmierelement deklariert ist, müssen Sie den Elementnamen qualifizieren. Weitere Informationen finden Sie unter [Gültigkeitsbereich in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarationen und Konstanten: Zusammenfassung](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)   
 [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
