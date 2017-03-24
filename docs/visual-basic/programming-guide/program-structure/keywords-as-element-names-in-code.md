---
title: "Keywords as Element Names in Code (Visual Basic) | Microsoft Docs"
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
  - "Visual Basic code, naming conventions"
  - "keywords [Visual Basic], in code"
  - "name conflicts"
  - "element names, in code"
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Keywords as Element Names in Code (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Jedes Programmelement \(z. B. Variablen, Klassen oder Member\) kann denselben Namen wie ein eingeschränktes Schlüsselwort haben.  Beispielsweise können Sie eine Variable mit dem Namen `Loop` erstellen.  Um jedoch auf diese Version der Variablen verweisen zu können, die denselben Namen wie das geschützte `Loop`\-Schlüsselwort aufweist, müssen Sie dem Namen entweder die vollständige qualifizierende Zeichenfolge voranstellen, oder ihn wie im folgenden Beispiel in eckige Klammern \(`[ ]`\) einschließen:  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 Wenn Sie keinen der beiden Schritte ausführen, geht Visual Basic davon aus, dass das systeminterne `Loop`\-Schlüsselwort verwendet wurde, und erzeugt einen Fehler, wie im folgenden Beispiel gezeigt:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 Die eckigen Klammern können beim Verweisen auf Formulare und Steuerelemente sowie bei der Deklaration einer Variablen oder der Definition einer Prozedur mit demselben Namen wie ein eingeschränktes Schlüsselwort verwendet werden.  Vollständige Namen oder eckige Klammern werden schnell einmal vergessen, und so kann es leicht passieren, dass sich Codefehler einschleichen und die Lesbarkeit leidet.  Deshalb wird davon abgeraten, eingeschränkte Schlüsselwörter als Namen von Programmelementen zu verwenden.  Falls jedoch in einer zukünftigen Version von Visual Basic ein neues Schlüsselwort definiert wird, das einen Konflikt mit dem Namen eines vorhandenen Formulars oder Steuerelements verursacht, können Sie mit diesem Verfahren Code so aktualisieren, dass er in der neuen Version fehlerfrei ausgeführt wird.  
  
> [!NOTE]
>  Ein Programm kann auch Elementnamen enthalten, die aus anderen Assemblys stammen, auf die verwiesen wird.  Wenn diese Namen einen Konflikt mit eingeschränkten Schlüsselwörtern verursachen, führt das Einschließen der Namen in eckige Klammern dazu, dass sie von Visual Basic als die von Ihnen definierten Elemente interpretiert werden.  
  
## Siehe auch  
 [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)