---
title: Name der &#39; &lt;Namen&gt;&#39; ist nicht deklariert
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords: BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a63ae74c7179d71756e2b9b4bf6b41a71ce12a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="name-39ltnamegt39-is-not-declared"></a>Name der &#39; &lt;Namen&gt;&#39; ist nicht deklariert
Eine Anweisung verweist auf ein Programmierelement, aber der Compiler ein Element mit genau diesem Namen kann nicht gefunden werden.  
  
 **Fehler-ID:** BC30451  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die Schreibweise des Namens in der verweisenden Anweisung. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Groß-/Kleinschreibung, wird jedoch eine andere Variante der Schreibweise als dem völlig anderen Namen betrachtet wird. Beachten Sie, dass der Unterstrich (`_`) Teil des Namens und daher Teil der Schreibweise ist.  
  
2.  Überprüfen Sie, ob Sie den Memberzugriffsoperator (`.`) zwischen einem Objekt und seinem Member. Wenn Sie z. B. ein <xref:System.Windows.Forms.TextBox> -Steuerelement namens `TextBox1`besitzen, müssen Sie für den Zugriff auf dessen <xref:System.Windows.Forms.TextBoxBase.Text%2A> -Eigenschaft `TextBox1.Text`eingeben. Wenn Sie stattdessen `TextBox1Text`eingeben, haben Sie einen anderen Namen erstellt.  
  
3.  Wenn die Schreibweise korrekt ist und die Syntax für alle Member Objektzugriff richtig ist, stellen Sie sicher, dass das Element deklariert wurde. Weitere Informationen finden Sie unter [deklarierten Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).  
  
4.  Wenn das Programmierelement deklariert wurde, überprüfen Sie, dass es sich im Gültigkeitsbereich befindet. Wenn die verweisende Anweisung außerhalb des Bereichs, der das Programmierelement deklariert ist, müssen Sie möglicherweise den Namen zu qualifizieren. Weitere Informationen finden Sie unter [Gültigkeitsbereich in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarationen und Konstanten: Zusammenfassung](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)  
 [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
