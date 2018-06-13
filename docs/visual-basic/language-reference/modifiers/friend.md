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
ms.openlocfilehash: d906fc8ada19f22059da44acbd76dd07dacd4801
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234588"
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)
Gibt an, dass eine oder mehrere deklarierte Programmierelemente nur innerhalb der Assembly zugegriffen werden, die ihre Deklaration enthält.  
  
## <a name="remarks"></a>Hinweise  
 In vielen Fällen möchten Sie die Programmierelemente, wie Klassen und Strukturen, die durch die gesamte Assembly, nicht nur von der Komponente verwendet werden, der sie deklariert. Allerdings können Sie nicht sinnvoll Code außerhalb der Assembly (z. B., wenn die Anwendung proprietären ist) zugänglich sein. Wenn Sie den Zugriff auf ein Element auf diese Weise beschränken möchten, können Sie sie deklarieren, indem die `Friend` Modifizierer.  
  
 Code in anderen Klassen, Strukturen und Module, die auf den gleichen kompiliert werden Assembly zugreifen kann alle der `Friend` Elemente in dieser Assembly.  
  
 `Friend` Zugriff ist häufig die bevorzugte für eine Anwendung Programmierelemente, und `Friend` ist der Standardzugriff von einer Schnittstelle, ein Modul, eine Klasse oder eine Struktur.  
  
 Sie können `Friend` nur auf das Modul, Schnittstelle oder Namespace-Ebene. Aus diesem Grund der Deklarationskontext für eine `Friend` Element muss eine Quelldatei, einen Namespace, eine Schnittstelle, ein Modul, eine Klasse oder eine Struktur sein; eine Prozedur kann nicht mehr.  

> [!NOTE]
> Sie können auch die [Protected Friend](protected-friend.md) Zugriffsmodifizierer, wodurch einen Klassenmember aus zugegriffen werden, in der betreffenden Klasse, die von abgeleiteten Klassen und aus der gleichen Assembly, in dem die Klasse definiert ist. Um den Zugriff auf ein Element innerhalb der Klasse und von abgeleiteten Klassen in der gleichen Assembly zu beschränken, verwenden Sie die [Private geschützte](private-protected.md) Zugriffsmodifizierer.

 Einen Vergleich der `Friend` und anderen Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
>  Sie können angeben, dass eine andere Assembly ein Friend-Assembly ist, womit Zugriff auf alle Typen und Member, die als markiert sind `Friend`. Weitere Informationen finden Sie unter [Friend-Assemblys](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).  
  
## <a name="example"></a>Beispiel  
 Die folgende Klasse verwendet die `Friend` Modifizierer, um andere Programmierelemente in derselben Assembly auf bestimmte Member zugreifen zu können.  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## <a name="usage"></a>Verwendung  
 Sie können die `Friend` Modifizierer in diesen Kontexten:  
  
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
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Geschützt privat](./private-protected.md)   
 [Protected Friend](./protected-friend.md)   
 [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
