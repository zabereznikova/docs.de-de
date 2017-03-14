---
title: "How to: Label Statements (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "colons (:)"
  - "statements [Visual Basic], labels"
  - ": separator character"
  - "Visual Basic code, labeling statements"
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# How to: Label Statements (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Anweisungsblöcke bestehen aus Codezeilen, in denen die Anweisungen durch Doppelpunkte voneinander getrennt sind.  Codezeilen, denen eine Zeichenfolge oder eine ganze Zahl als Kennzeichnung vorangestellt ist, sind *bezeichnet*.  Anweisungsbezeichnungen werden verwendet, um Codezeilen für die Verwendung mit Anweisungen wie `On Error Goto` zu kennzeichnen.  
  
 Bezeichnungen können jedes gültige Bezeichner\-solche Visual Basic, die während der Programmierungs\- ELEMENTS\-oder Zahlen literale identifizieren.  Bezeichnungen müssen immer am Anfang der Zeile des Quellcodes stehen und von einem Doppelpunkt gefolgt werden, unabhängig davon, ob in derselben Zeile eine Anweisung steht oder nicht.  
  
 Der Compiler erkennt Bezeichnungen dadurch, dass er überprüft, ob der Anfang der Zeile mit einem bereits definierten Bezeichner übereinstimmt.  Ist dies nicht der Fall, nimmt der Compiler an, dass es sich um einen Bezeichner handelt.  
  
 Marken verfügen über eigene Deklarationsbereiche und verursachen keine Konflikte mit anderen Bezeichnern.  Der Gültigkeitsbereich einer Bezeichnung erstreckt sich über den Körper der Methode.  Im Falle von Mehrdeutigkeiten hat die Deklaration der Bezeichnung Vorrang.  
  
> [!NOTE]
>  Bezeichnungen können nur für ausführbare Anweisungen innerhalb von Methoden verwendet werden.  
  
### So bezeichnen Sie eine Codezeile  
  
-   Platzieren Sie am Anfang der Zeile im Quellcode einen Bezeichner, gefolgt von einem Doppelpunkt.  
  
     Die folgenden Codezeilen sind z. B. mit `Jump` bzw. `120` bezeichnet:  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## Siehe auch  
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)