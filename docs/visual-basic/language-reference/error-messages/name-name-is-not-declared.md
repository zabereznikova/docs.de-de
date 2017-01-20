---
title: "Name &#39;&lt;name&gt;&#39; is not declared | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30451"
  - "vbc30451"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30451"
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Name &#39;&lt;name&gt;&#39; is not declared
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Eine Anweisung verweist auf ein Programmierelement, der Compiler kann jedoch kein Element mit genau diesem Namen finden.  
  
 **Fehler\-ID:** BC30451  
  
### So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die Schreibweise des Namens in der verweisenden Anweisung.  In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] wird nicht nach Groß\- und Kleinschreibung unterschieden, andere Abweichungen der Schreibweise gelten jedoch als völlig anderer Name.  Der Unterstrich \(`_`\) ist Teil des Namens und daher bei der Schreibweise zu berücksichtigen.  
  
2.  Prüfen Sie, ob Sie den Memberzugriffsoperator \(`.`\) zwischen einem Objekt und seinem Member eingefügt haben.  Wenn Sie z. B. auf die <xref:System.Windows.Forms.TextBoxBase.Text%2A>\-Eigenschaft eines <xref:System.Windows.Forms.TextBox>\-Steuerelements mit dem Namen `TextBox1` zugreifen möchten, müssen Sie `TextBox1.Text` eingeben.  Wenn Sie stattdessen `TextBox1Text` eingeben, haben Sie einen anderen Namen erstellt.  
  
3.  Wenn die Schreibweise stimmt und die Syntax des Objektmemberzugriffs richtig ist, überprüfen Sie, ob das Element deklariert wurde.  Weitere Informationen finden Sie unter [Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).  
  
4.  Wenn das Programmierelement deklariert wurde, überprüfen Sie, ob es sich innerhalb des Gültigkeitsbereichs befindet.  Wenn sich die verweisende Anweisung außerhalb des Bereichs befindet, in dem das Programmierelement deklariert wird, müssen Sie eventuell den Elementnamen qualifizieren.  Weitere Informationen finden Sie unter [Scope in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## Siehe auch  
 [Declarations and Constants Summary](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)   
 [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)