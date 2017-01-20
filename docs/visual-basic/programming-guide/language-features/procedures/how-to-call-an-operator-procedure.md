---
title: "How to: Call an Operator Procedure (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
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
  - "operator procedures, calling"
  - "procedures, operator"
  - "procedure calls, operator overloading"
  - "syntax, Operator procedures"
  - "operators [Visual Basic], overloading"
  - "return values, Operator procedures"
  - "overloaded operators, calling"
  - "operator overloading"
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Call an Operator Procedure (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Zum Aufrufen einer Operatorprozedur verwenden Sie das Operatorsymbol in einem Ausdruck.  Im Fall eines Konvertierungsoperators rufen Sie die Prozedur [CType\-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) auf, um einen Wert in einen anderen Datentyp zu konvertieren.  
  
 Operatorprozeduren werden nicht explizit aufgerufen.  Der Operator oder die `CType`\-Funktion wird in einer Zuweisungsanweisung oder in einem Ausdruck auf die gleiche Art verwendet wie üblicherweise Operatoren.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] ruft die Operatorprozedur auf.  
  
 Das Definieren eines Operators für eine Klasse oder Struktur wird auch als *Überladen* bezeichnet.  
  
### So rufen Sie eine Operatorprozedur auf  
  
1.  Verwenden Sie das Operatorsymbol in einem Ausdruck in der gewohnten Weise.  
  
2.  Stellen Sie sicher, dass die Datentypen der Operanden für den Operator geeignet sind und die richtige Reihenfolge aufweisen.  
  
3.  Der Operator trägt wie erwartet zum Wert des Ausdrucks bei.  
  
### So rufen Sie eine Konvertierungsoperatorprozedur auf  
  
1.  Verwenden Sie `CType` in einem Ausdruck.  
  
2.  Stellen Sie sicher, dass die Datentypen der Operanden für die Konvertierung geeignet sind und die richtige Reihenfolge aufweisen.  
  
3.  `CType` ruft die Konvertierungsoperatorprozedur auf und gibt den konvertierten Wert zurück.  
  
## Beispiel  
 Im folgenden Beispiel werden zwei <xref:System.TimeSpan>\-Strukturen erstellt und zusammengefügt. Anschließend wird das Ergebnis in einer dritten <xref:System.TimeSpan>\-Struktur gespeichert.  Die <xref:System.TimeSpan>\-Struktur definiert Operatorprozeduren, die mehrere Standardoperatoren überladen.  
  
 [!code-vb[VbVbcnProcedures#29](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-call-an-operator-pro_1.vb)]  
  
 Da <xref:System.TimeSpan> den standardmäßigen Operator `+` überlädt, wird im vorhergehenden Beispiel eine Operatorprozedur aufgerufen, wenn der Wert von `combinedSpan` berechnet wird.  
  
 Ein Beispiel für den Aufruf einer Konvertierungsoperatorprozedur finden Sie unter [How to: Use a Class that Defines Operators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md).  
  
## Kompilieren des Codes  
 Stellen Sie sicher, dass der zu verwendende Operator durch die Klasse oder die Struktur definiert wird, die Sie verwenden.  
  
## Siehe auch  
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define an Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)