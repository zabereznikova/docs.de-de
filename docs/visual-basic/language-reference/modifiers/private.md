---
title: "Private (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Private"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Private keyword"
  - "Private keyword, syntax"
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Private (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt an, dass ein Zugriff auf mindestens ein oder mehrere deklarierte Programmierelemente nur aus ihrem Deklarationskontext einschließlich darin enthaltener Typen heraus möglich ist.  
  
## Hinweise  
 Wenn ein Programmierelement eine proprietäre Funktionalität darstellt oder vertrauliche Daten enthält, empfiehlt es sich, den Zugriff darauf so stark wie möglich zu beschränken.  Die maximale Beschränkung erreichen Sie, wenn Sie den Zugriff nur dem Modul, der Klasse oder der Struktur gestatten, in der das Element definiert wird.  Wenn Sie den Zugriff auf ein Element auf diese Weise beschränken möchten, können Sie es mit `Private` deklarieren.  
  
## Regeln  
  
-   **Deklarationskontext.** `Private` kann nur auf Modulebene verwendet werden.  Dies bedeutet, dass der Deklarationskontext für ein `Private`\-Element ein Modul, eine Klasse oder eine Struktur sein muss und es sich nicht um eine Quelldatei, einen Namespace, eine Schnittstelle oder eine Prozedur handeln kann.  
  
## Verhalten  
  
-   **Zugriffsebene.** Sämtlicher Code innerhalb eines Deklarationskontexts kann auf seine `Private`\-Elemente zugreifen.  Hierzu gehört auch Code innerhalb eines enthaltenen Typs, z. B. eine geschachtelte Klasse oder ein Zuweisungsausdruck in einer Enumeration.  Kein Code außerhalb des Deklarationskontexts kann auf die `Private`\-Elemente zugreifen.  
  
-   **Zugriffsmodifizierer.** Die Schlüsselwörter für die Angabe der Zugriffsebene werden als *Zugriffsmodifizierer* bezeichnet.  Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Der `Private`\-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
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
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)