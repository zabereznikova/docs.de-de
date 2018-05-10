---
title: '&#39;Legen Sie&#39; Accessor der Eigenschaft &#39; &lt;Propertyname&gt; &#39; kann nicht zugegriffen werden'
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: d047d03755de89d4740482db4845d5db72003ac0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="39set39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a>&#39;Legen Sie&#39; Accessor der Eigenschaft &#39; &lt;Propertyname&gt; &#39; kann nicht zugegriffen werden
Eine Anweisung versucht, den Wert einer Eigenschaft zu speichern, wenn sie keinen Zugriff auf der Eigenschaft hat `Set` Prozedur.  
  
 Wenn die [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md) RuntimeCompatibility mit einer restriktiveren Zugriffsebene als seine [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md), beim Festlegen der Wert der Eigenschaft in den folgenden Fällen fehlschlagen:  
  
-   Die `Set` Anweisung RuntimeCompatibility [Private](../../../visual-basic/language-reference/modifiers/private.md) und der aufrufende Code außerhalb der Klasse oder Struktur, die in der die Eigenschaft definiert ist.  
  
-   Die `Set` Anweisung RuntimeCompatibility [geschützte](../../../visual-basic/language-reference/modifiers/protected.md) und der aufrufende Code befindet sich nicht in der Klasse oder Struktur, die in der die Eigenschaft definiert ist, noch in einer abgeleiteten Klasse.  
  
-   Die `Set` Anweisung RuntimeCompatibility ["Friend"](../../../visual-basic/language-reference/modifiers/friend.md) und der aufrufende Code ist nicht in der gleichen Assembly, in dem die Eigenschaft definiert wird.  
  
 **Fehler-ID:** BC31102  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn Sie die Kontrolle des Quellcodes die-Eigenschaft definiert haben, sollten Sie deklarieren die `Set` Prozedur mit die gleiche Zugriffsebene wie die Eigenschaft selbst.  
  
-   Wenn Sie keine Kontrolle über den Quellcode der-Eigenschaft definiert wird, oder Sie einschränken, müssen die `Set` Prozedur Zugriffsebene mehr als die Eigenschaft selbst, versuchen Sie es so verschieben Sie die Anweisung, die den Wert der Eigenschaft auf einen Codebereich festgelegt, der besseren Zugriff auf die Diese Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenprozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
