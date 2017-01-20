---
title: "How to: Test Whether Two Objects Are the Same (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables [Visual Basic], reference"
  - "Is operator [Visual Basic], comparing objects"
  - "reference variables"
  - "variables [Visual Basic], referring to same object"
  - "objects [Visual Basic], variables referring to same"
  - "Visual Basic code, operators"
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Test Whether Two Objects Are the Same (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Wenn zwei auf Objekte verweisende Variablen vorhanden sind, können Sie mit dem Operator `Is` oder dem Operator `IsNot` überprüfen, ob sie auf dieselbe Instanz verweisen.  
  
### So überprüfen Sie, ob zwei Objekte identisch sind  
  
-   Verwenden Sie den [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) oder den [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) mit den zwei Variablen als Operanden.  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-obj_1.vb)]  
  
 Möglicherweise soll eine bestimmte Aktion ausgeführt werden, je nachdem, ob zwei Objekte auf dieselbe Instanz verweisen.  Im vorherigen Beispiel wird das Steuerelement `c` mit dem aktiven Steuerelement in dem Formular `f` verglichen.  Wenn kein aktives Steuerelement vorhanden ist oder wenn ein aktives Steuerelement vorhanden ist, das jedoch nicht dieselbe Instanz wie `c` ist, schlägt die `If`\-Anweisung fehl, und die Prozedur wird ohne weitere Verarbeitung beendet.  
  
 Ob Sie `Is` oder `IsNot` verwenden, hängt davon ab, was für Sie praktischer ist.  Der eine Operator ist in einem bestimmten Ausdruck eventuell besser lesbar als der andere.  
  
## Siehe auch  
 [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)