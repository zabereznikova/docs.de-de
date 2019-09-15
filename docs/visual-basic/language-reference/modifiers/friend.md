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
ms.openlocfilehash: 2a5a2d6b9d99693a551480fa047cedf42888fdf3
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969054"
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)
Gibt an, dass auf ein oder mehrere deklarierte Programmier Elemente nur innerhalb der Assembly, die ihre Deklaration enthält, zugegriffen werden kann.  
  
## <a name="remarks"></a>Hinweise  
 In vielen Fällen sollen Programmier Elemente, wie z. b. Klassen und Strukturen, von der gesamten Assembly verwendet werden, nicht nur von der Komponente, von der Sie deklariert werden. Allerdings möchten Sie möglicherweise nicht, dass Sie über Code außerhalb der Assembly zugänglich sind (z. b. wenn die Anwendung proprietär ist). Wenn Sie den Zugriff auf ein Element auf diese Weise einschränken möchten, können Sie es mit dem `Friend` -Modifizierer deklarieren.  
  
 Code in anderen Klassen, Strukturen und Modulen, die in derselben Assembly kompiliert werden, kann auf alle `Friend` Elemente in der Assembly zugreifen.  
  
 `Friend`der Zugriff ist oft die bevorzugte Ebene für die Programmier Elemente einer Anwendung, `Friend` und ist die Standard Zugriffsebene einer Schnittstelle, eines Moduls, einer Klasse oder einer Struktur.  
  
 Sie können nur `Friend` auf der Ebene "Module", "Interface" oder "Namespace" verwenden. Daher muss der Deklarations Kontext für `Friend` ein-Element eine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Klasse oder eine Struktur sein. es kann sich dabei nicht um eine Prozedur handeln.  

> [!NOTE]
> Sie können auch den [geschützten Friend](protected-friend.md) -Zugriffsmodifizierer verwenden, der einen Klassenmember aus dieser Klasse, aus abgeleiteten Klassen und aus der gleichen Assembly, in der die Klasse definiert ist, zugänglich macht. Um den Zugriff auf ein Member innerhalb seiner Klasse und von abgeleiteten Klassen in derselben Assembly einzuschränken, verwenden Sie den [privaten geschützten](private-protected.md) Zugriffsmodifizierer.

 Einen Vergleich `Friend` und die anderen Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
> Sie können angeben, dass eine andere Assembly eine Friend-Assembly ist, die es ermöglicht, auf alle Typen und Member zuzugreifen `Friend`, die als markiert sind. Weitere Informationen finden Sie unter [Friend-Assemblys](../../../standard/assembly/friend.md).

## <a name="example"></a>Beispiel  
 Die folgende Klasse verwendet den `Friend` -Modifizierer, damit andere Programmier Elemente innerhalb derselben Assembly auf bestimmte Member zugreifen können.  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a>Verwendung  
 Sie können den `Friend` -Modifizierer in diesen Kontexten verwenden:  
  
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
- [Öffentlich](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
