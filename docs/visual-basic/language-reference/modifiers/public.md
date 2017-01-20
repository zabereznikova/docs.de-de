---
title: "Public (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Public"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Public keyword"
  - "Public keyword, syntax"
  - "Public access modifier"
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Public (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt an, dass mindestens ein deklariertes Programmierelement über keine Zugriffsbeschränkungen verfügt.  
  
## Hinweise  
 Wenn Sie eine Komponente oder einen Satz von Komponenten, beispielsweise eine Klassenbibliothek, veröffentlichen, soll in der Regel jeder Code, der mit der Assembly interagiert, auf die Programmierelemente zugreifen können.  Wenn Sie solchen unbegrenzten Zugriff auf ein Element gewähren möchten, können Sie es mit `Public` deklarieren.  
  
 Public ist die normale Zugriffsebene für ein Programmierelement, wenn Sie den Zugriff darauf nicht beschränken müssen.  Die standardmäßige Zugriffsebene für ein Element, das in einer Schnittstelle, einem Modul, einer Klasse oder einer Struktur deklariert wird, ist `Public`, wenn Sie es nicht anderweitig deklarieren.  
  
## Regeln  
  
-   **Deklarationskontext.** Sie können `Public` nur auf Modul\-, Schnittstellen\- oder Namespaceebene verwenden.  Dies bedeutet, dass der Deklarationskontext für ein `Public`\-Element eine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Klasse oder eine Struktur sein muss und keine Prozedur sein kann.  
  
## Verhalten  
  
-   **Zugriffsebene.** Code, der auf ein Modul, eine Klasse oder eine Struktur zugreifen kann, kann auch auf die entsprechenden `Public`\-Elemente zugreifen.  
  
-   **Standardzugriff.** Für lokale Variablen in einer Prozedur gilt standardmäßig der öffentliche Zugriff. Für diese Variablen können keine Zugriffsmodifizierer verwendet werden.  
  
-   **Zugriffsmodifizierer.** Die Schlüsselwörter für die Angabe der Zugriffsebene werden als *Zugriffsmodifizierer* bezeichnet.  Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Der `Public`\-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
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
  
 [Operator\-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property\-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub\-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Siehe auch  
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)