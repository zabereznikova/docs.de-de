---
title: "How to: Define an Operator (Visual Basic) | Microsoft Docs"
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
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "operators [Visual Basic], defining"
  - "procedures, operator"
  - "Visual Basic code, operators"
  - "syntax, Operator procedures"
  - "operators [Visual Basic], overloading"
  - "operator procedures, about operator procedures"
  - "return values, Operator procedures"
  - "operator overloading"
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Define an Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Wenn Sie eine Klasse oder Struktur definiert haben, können Sie das Verhalten eines Standardoperators \(z. B. `*`, `<>` oder `And`\) definieren, wenn einer oder beide der Operanden den Typ der Klasse bzw. Struktur aufweisen.  
  
 Definieren Sie den Standardoperator als eine Operatorprozedur innerhalb der Klasse bzw. Struktur.  Alle Operatorprozeduren müssen `Public` `Shared` sein.  
  
 Das Definieren eines Operators für eine Klasse oder Struktur wird auch als *Überladen* bezeichnet.  
  
## Beispiel  
 Im folgenden Beispiel wird der Operator `+` für eine Struktur mit dem Namen `height`definiert.  Die Struktur verwendet in Fuß und Zoll gemessene Höhen.  Ein *Zoll* entspricht 2,54 Zentimetern, und ein *Fuß* ist 12 Zoll.  Um normalisierte Werte \(Zoll \< 12,0\) zu gewährleisten, führt der Konstruktor die *Modulo*\-12\-Arithmetik aus.  Der Operator `+` verwendet den Konstruktor, um normalisierte Werte zu generieren.  
  
 [!code-vb[VbVbcnProcedures#25](./codesnippet/VisualBasic/how-to-define-an-operator_1.vb)]  
  
 Sie können die `height` \-Struktur mit dem folgenden Code testen.  
  
 [!code-vb[VbVbcnProcedures#26](./codesnippet/VisualBasic/how-to-define-an-operator_2.vb)]  
  
 Weitere Informationen und Beispiele finden Sie unter [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).  
  
## Siehe auch  
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [How to: Call an Operator Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)   
 [How to: Use a Class that Defines Operators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)   
 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Operator Mod](../../../../visual-basic/language-reference/operators/mod-operator.md)