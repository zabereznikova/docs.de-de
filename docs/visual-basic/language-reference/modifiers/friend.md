---
title: Friend (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: 9be3200300de308a70559536905d1e118a4a5fe4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616198"
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)
Gibt an, dass eine oder mehrere deklarierte Programmierelemente nur innerhalb der Assembly zugegriffen werden, die ihre Deklaration enthält.  
  
## <a name="remarks"></a>Hinweise  
 In vielen Fällen möchten Sie die Programmierelemente wie Klassen und Strukturen, um die gesamte Assembly, nicht nur von der Komponente verwendet werden, der sie deklariert. Jedoch möglicherweise nicht diese sollen von Code außerhalb der Assembly (z. B., wenn die Anwendung proprietäre ist) zugegriffen werden. Wenn Sie den Zugriff auf ein Element auf diese Weise beschränken möchten, können Sie sie deklarieren, indem die `Friend` Modifizierer.  
  
 Code in anderen Klassen, Strukturen und -Module, die auf die gleiche kompiliert werden Assembly kann auf alle zugreifen der `Friend` Elemente in dieser Assembly.  
  
 `Friend` Zugriff ist häufig die bevorzugte für Programmierelemente von einer Anwendung, und `Friend` der Standardzugriff von einer Schnittstelle, ein Modul, eine Klasse oder eine Struktur ist.  
  
 Sie können `Friend` nur auf das Modul, Schnittstelle oder Namespace-Ebene. Aus diesem Grund der Deklarationskontext für eine `Friend` Element muss eine Quelldatei, einem Namespace, eine Schnittstelle, ein Modul, eine Klasse oder eine Struktur sein und keine Prozedur sein.  

> [!NOTE]
> Sie können auch die [Protected Friend](protected-friend.md) Zugriffsmodifizierer, wodurch einen Klassenmember kann innerhalb dieser Klasse, aus der gleichen Assembly, die in der die Klasse definiert ist und von abgeleiteten Klassen zugegriffen werden. Zum Einschränken des Zugriffs auf ein Element innerhalb seiner Klasse und von abgeleiteten Klassen in der gleichen Assembly, die Sie verwenden die [Private Protected](private-protected.md) Zugriffsmodifizierer.

 Einen Vergleich der `Friend` und die andere Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
>  Sie können angeben, dass eine andere Assembly Friend-Assembly, die ermöglicht, damit ein Zugriff auf alle Typen und Member, die als markiert sind `Friend`. Weitere Informationen finden Sie unter [Friend-Assemblys](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).  
  
## <a name="example"></a>Beispiel  
 Die folgende Klasse verwendet die `Friend` Modifizierer, um anderen Programmierungselementen innerhalb der gleichen Assembly auf bestimmte Member zugreifen zu können.  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## <a name="usage"></a>Verwendung  
 Sie können die `Friend` Modifizierer in den folgenden Kontexten:  
  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
