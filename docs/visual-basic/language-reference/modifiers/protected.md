---
title: "Protected (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Protected"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Protected Friend keyword combination"
  - "Protected keyword, and Friend"
  - "Protected keyword, syntax"
  - "Protected access modifier"
  - "Protected keyword"
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Protected (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt an, dass auf ein oder mehrere deklarierte Programmierelement\/e nur aus seiner bzw. ihrer eigenen Klasse oder aus einer abgeleiteten Klasse heraus zugegriffen werden kann.  
  
## Hinweise  
 Manchmal enthält ein in einer Klasse deklariertes Programmierelement vertrauliche Daten oder eingeschränkten Code, und Sie möchten den Zugriff auf das Element begrenzen.  Wenn die Klasse jedoch vererbbar ist und Sie eine Hierarchie abgeleiteter Klassen erwarten, kann es notwenig sein, dass diese abgeleiteten Klassen auf die Daten oder den Code zugreifen.  In einem solchen Fall soll sowohl aus der Basisklasse als auch aus allen abgeleiteten Klassen heraus auf das Element zugegriffen werden können.  Wenn Sie den Zugriff auf ein Element auf diese Weise beschränken möchten, können Sie es mit `Protected` deklarieren.  
  
## Regeln  
  
-   **Deklarationskontext.** `Protected` kann nur auf Klassenebene verwendet werden.  Dies bedeutet, dass der Deklarationskontext für ein `Protected`\-Element eine Klasse, aber keine Quelldatei, kein Namespace, keine Schnittstelle, kein Modul, keine Struktur und keine Prozedur sein kann.  
  
-   **Kombinierte Modifizierer.** Sie können den `Protected`\-Modifizierer in Verbindung mit dem [Friend](../../../visual-basic/language-reference/modifiers/friend.md)\-Modifizierer in derselben Deklaration verwenden.  Diese Kombination bewirkt, dass von überall in der Assembly, also von Code, der zur eigenen Klasse und einer abgeleiteten Klasse gehört, auf die deklarierten Elemente zugegriffen werden kann.  Sie können `Protected Friend` nur für Member von Klassen angeben.  
  
## Verhalten  
  
-   **Zugriffsebene.** Jeglicher Code innerhalb einer Klasse kann auf die Elemente seiner Klasse zugreifen.  Im Code jeder Klasse, die sich von einer Basisklasse herleitet, kann auf alle `Protected`\-Elemente der Basisklasse zugegriffen werden.  Dies gilt für alle Generationen der Ableitung.  Eine Klasse kann also auf `Protected`\-Elemente der Basisklasse der Basisklasse usw. zugreifen.  
  
     Dieser Zugriffstyp ist dem Friend\-Zugriff weder über\- noch untergeordnet.  
  
-   **Zugriffsmodifizierer.** Die Schlüsselwörter für die Angabe der Zugriffsebene werden als *Zugriffsmodifizierer* bezeichnet.  Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Der `Protected`\-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const\-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare\-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate\-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim\-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum\-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event\-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function\-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface\-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Property\-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub\-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Siehe auch  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)