---
title: Auf den Set-Accessor der <propertyname>-Eigenschaft kann nicht zugegriffen werden.
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: cf0158692c1154a8a903c893ba287e51c1e34ac8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593271"
---
# <a name="set-accessor-of-property-propertyname-is-not-accessible"></a>"Set-Accessor der Eigenschaft"\<Propertyname >' kann nicht zugegriffen werden
Eine Anweisung versucht, den Wert einer Eigenschaft zu speichern, wenn sie den Zugriff auf die Eigenschaft keinen `Set` Verfahren.  
  
 Wenn die [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md) mit einem restriktiveren Zugriffsebene als markiert ist seine [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), beim Festlegen der Wert der Eigenschaft kann in den folgenden Fällen fehlschlagen:  
  
- Die `Set` Anweisung RuntimeCompatibility [Private](../../../visual-basic/language-reference/modifiers/private.md) und der aufrufende Code ist außerhalb der Klasse oder Struktur, in dem die Eigenschaft definiert ist.  
  
- Die `Set` Anweisung RuntimeCompatibility [geschützte](../../../visual-basic/language-reference/modifiers/protected.md) und der aufrufende Code ist nicht in der Klasse oder Struktur, die in der die Eigenschaft definiert ist, noch in einer abgeleiteten Klasse.  
  
- Die `Set` Anweisung RuntimeCompatibility [Friend](../../../visual-basic/language-reference/modifiers/friend.md) und der aufrufende Code ist nicht in der gleichen Assembly, in dem die Eigenschaft definiert wird.  
  
 **Fehler-ID:** BC31102  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenn Sie die Kontrolle über den Quellcode, der die Eigenschaft haben, sollten Sie deklarieren die `Set` Prozedur mit die gleiche Zugriffsebene wie die Eigenschaft selbst.  
  
- Wenn Sie keine Kontrolle über den Quellcode, der die Eigenschaft definieren, oder Sie einschränken, müssen die `Set` Prozedur Zugriffsebene mehr als die Eigenschaft selbst, versuchen Sie es, um die Anweisung zu verschieben, die den Wert der Eigenschaft um einen Codebereich festlegt, die besseren Zugriff auf die Diese Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch

- [Eigenschaftenprozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
