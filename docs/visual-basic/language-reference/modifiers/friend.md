---
title: Friend (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: df0e8ad1990fe7a1aa495e1794c942813cffb5bc
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)
Gibt an, dass eine oder mehrere deklarierte Programmierelemente nur innerhalb der Assembly zugegriffen werden, die ihre Deklaration enthält.  
  
## <a name="remarks"></a>Hinweise  
 In vielen Fällen möchten Sie die Programmierelemente, wie Klassen und Strukturen, die durch die gesamte Assembly, nicht nur von der Komponente verwendet werden, der sie deklariert. Allerdings können Sie nicht sinnvoll Code außerhalb der Assembly (z. B., wenn die Anwendung proprietären ist) zugänglich sein. Wenn Sie den Zugriff auf ein Element auf diese Weise beschränken möchten, können Sie sie deklarieren, indem die `Friend` Modifizierer.  
  
 Code in anderen Klassen, Strukturen und Module, die auf den gleichen kompiliert werden Assembly zugreifen kann alle der `Friend` Elemente in dieser Assembly.  
  
 `Friend`Zugriff ist häufig die bevorzugte für eine Anwendung Programmierelemente, und `Friend` ist der Standardzugriff von einer Schnittstelle, ein Modul, eine Klasse oder eine Struktur.  
  
 Sie können `Friend` nur auf das Modul, Schnittstelle oder Namespace-Ebene. Aus diesem Grund der Deklarationskontext für eine `Friend` Element muss eine Quelldatei, einen Namespace, eine Schnittstelle, ein Modul, eine Klasse oder eine Struktur sein; eine Prozedur kann nicht mehr.  
  
 Können Sie die `Friend` Modifizierer in Verbindung mit der [geschützte](../../../visual-basic/language-reference/modifiers/protected.md) Modifizierer in der gleichen Deklaration. Diese Kombination überträgt sowohl `Friend` und geschützten Zugriff auf deklarierte Elemente, sodass sie über eine beliebige Stelle in der gleichen Assembly, von ihrer eigenen Klasse und von abgeleiteten Klassen zugänglich sind. Sie können angeben, `Protected Friend` nur auf Member von Klassen.  
  
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
 [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
