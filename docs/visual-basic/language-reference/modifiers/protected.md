---
title: Protected (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d0cc7a0cb626a9ec8e2a0e47abc02e5268aed56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="protected-visual-basic"></a>Protected (Visual Basic)
Gibt an, dass eine oder mehrere deklarierte Programmierelemente nur aus ihrer eigenen Klasse oder von einer abgeleiteten Klasse zugegriffen werden.  
  
## <a name="remarks"></a>Hinweise  
 Manchmal enthält ein Programmierelement in einer Klasse deklariert, vertrauliche Daten oder eingeschränkten Code, und Sie den Zugriff auf das Element einschränken möchten. Jedoch wenn die Klasse vererbbar ist, und Sie erwarten, eine Hierarchie von abgeleiteten Klassen dass, es für diese abgeleiteten Klassen den Zugriff auf die Daten oder Code möglicherweise erforderlich. In einem solchen Fall möchten Sie das Element aus der Basisklasse und aus allen abgeleiteten Klassen zugegriffen werden kann. Um den Zugriff auf ein Element auf diese Weise beschränken möchten, deklarieren Sie es mit `Protected`.  
  
## <a name="rules"></a>Regeln  
  
-   **Deklarationskontext.** Sie können `Protected` nur auf Klassenebene. Dies bedeutet, dass der Deklarationskontext für eine `Protected` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich.  
  
-   **Kombinierte Modifizierer.** Sie können die `Protected` Modifizierer zusammen mit der ["Friend"](../../../visual-basic/language-reference/modifiers/friend.md) Modifizierer in der gleichen Deklaration. Diese Kombination wird die deklarierte Elemente an einer beliebigen Stelle in der gleichen Assembly, von ihrer eigenen Klasse und von abgeleiteten Klassen zugegriffen werden. Sie können angeben, `Protected Friend` nur auf Member von Klassen.  
  
## <a name="behavior"></a>Verhalten  
  
-   **Zugriffsebene.** Der gesamte Code in einer Klasse kann ihre Elemente zugreifen. Code in einer Klasse, die von einer Basisklasse abgeleitet ist, kann auf alle zugreifen die `Protected` Elemente der Basisklasse. Dies gilt für alle Generationen der Ableitung. Dies bedeutet, dass eine Klasse zugreifen kann `Protected` Elemente der Basisklasse der Basisklasse und So weiter.  
  
     Geschützter Zugriff ist eine Obermenge oder eine Teilmenge der Friend-Zugriff.  
  
-   **Zugriffsmodifizierer.** Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*. Einen Vergleich der Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Der `Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
