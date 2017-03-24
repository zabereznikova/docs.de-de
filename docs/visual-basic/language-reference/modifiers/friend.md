---
title: "Friend (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Friend"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Friend-Schlüsselwort"
  - "Friend-Zugriffsmodifizierer"
  - "Friend-Schlüsselwort, Syntax"
  - "Protected Friend-Schlüsselwortkombination"
  - "Friend-Schlüsselwort, und Protected"
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# Friend (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt an, dass auf ein oder mehrere deklarierte Programmierelemente nur aus der Assembly mit der Deklaration zugegriffen werden kann.  
  
## Hinweise  
 In vielen Fällen kann es wünschenswert sein, dass Programmierelemente wie Klassen und Strukturen von der gesamten Assembly verwendet werden, statt nur von der Komponente, mit der sie deklariert werden.  Sie sollten sie nicht von Code außerhalb der Assembly zugegriffen werden können \(beispielsweise, wenn die Anwendung herstellereigen ist\).  Wenn Sie den Zugriff auf ein Element auf diese Weise beschränken möchten, können Sie ihn deklarieren, indem Sie den `Friend`\-Modifizierer verwenden.  
  
 Code in anderen Klassen, Strukturen oder Modulen, die in derselben Assembly kompiliert werden, kann auf alle `Friend`\-Elemente innerhalb dieser Assembly zugreifen.  
  
 `Friend` Zugriff ist häufig die bevorzugte Ebene für die Programmierelemente einer Anwendung, und `Friend` ist der Standardzugriff, der von einer Schnittstelle, einem Modul, einer Klasse oder Struktur einstellen.  
  
 Sie können `Friend` nur auf dem Modul, der Schnittstelle oder Namespaceebene keine verwenden.  Daher muss der Deklarationskontext für ein `Friend`\-Element eine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Klasse oder Struktur sein; Es kann keine Prozedur sein.  
  
 Sie können den `Friend`\-Modifizierer in Verbindung mit dem [Protected](../../../visual-basic/language-reference/modifiers/protected.md)\-Modifizierer in der gleichen Deklaration verwenden.  Diese Kombination konferiert sowohl `Friend` Zugriff und geschützter Zugriff auf den deklarierten Elementen, und sind daher überall in der Assembly, von ihrer eigenen Klasse und von abgeleiteten Klassen zugreifen.  Sie können `Protected Friend` nur für Member von Klassen angeben.  
  
 Einen Vergleich der `Friend` und anderen Zugriffsmodifizierern, finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
>  Sie können angeben, dass eine andere Assembly eine Friend\-Assembly ist, deren ermöglicht, alle Typen und Member zugreifen, die als `Friend` gekennzeichnet werden.  Weitere Informationen finden Sie unter [Friend\-Assemblys](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Beispiel  
 Die folgende Klasse ermöglicht anderen Programmierelementen innerhalb der gleichen Assembly, mithilfe des `Friend`\-Modifizierers auf bestimmte Member zuzugreifen.  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## Verwendung  
 Sie können den `Friend`\-Modifizierer in diesen Kontexten verwenden:  
  
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const\-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare\-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate\-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim\-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum\-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event\-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function\-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface\-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Module\-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [Property\-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub\-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Siehe auch  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)