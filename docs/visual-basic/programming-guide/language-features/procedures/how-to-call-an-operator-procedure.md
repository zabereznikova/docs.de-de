---
title: 'Gewusst wie: Aufrufen einer Operatorprozedur (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- operator procedures, calling
- procedures, operator
- procedure calls, operator overloading
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- overloaded operators, calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2403e7a8270c17a8db5417cd8394fd47c373d493
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>Gewusst wie: Aufrufen einer Operatorprozedur (Visual Basic)
Sie aufrufen eine Operatorprozedur verwenden Sie das Operatorsymbol in einem Ausdruck. Im Fall eines Konvertierungsoperators rufen Sie die [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) einen Wert von einem Datentyp in einen anderen konvertiert.  
  
 Operatorprozeduren werden nicht explizit aufrufen. Sie verwenden einfach den Operator oder die `CType` -Funktion in eine Zuweisung oder einen Ausdruck ein, wie Sie in der Regel einen Operator. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Ruft die Operatorprozedur auf.  
  
 Definieren eines Operators für eine Klasse oder Struktur ist die Abkürzung *überladen* des Operators.  
  
### <a name="to-call-an-operator-procedure"></a>Aufrufen eine Operatorprozedur  
  
1.  Verwenden Sie das Operatorsymbol in einem Ausdruck auf die übliche Weise.  
  
2.  Achten Sie darauf, dass die Datentypen der Operanden für den Operator an, und in der richtigen Reihenfolge sind.  
  
3.  Der Operator trägt auf den Wert des Ausdrucks wie erwartet.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>Aufrufen einer Konvertierungsoperatorprozedur  
  
1.  Verwendung `CType` innerhalb eines Ausdrucks.  
  
2.  Achten Sie darauf, dass die Datentypen der Operanden für die Konvertierung an, und in der richtigen Reihenfolge sind.  
  
3.  `CType`Ruft die Konvertierungsoperatorprozedur, und gibt den konvertierten Wert zurück.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt zwei <xref:System.TimeSpan>Strukturen, diese zusammenfügt und speichert das Ergebnis in einer dritten <xref:System.TimeSpan>Struktur.</xref:System.TimeSpan> </xref:System.TimeSpan> Der <xref:System.TimeSpan>-Struktur definiert Operatorprozeduren, die mehrere Standardoperatoren überladen.</xref:System.TimeSpan>  
  
 [!code-vb[VbVbcnProcedures&#29;](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 Da <xref:System.TimeSpan>überlädt den Standard `+` Operator wird im vorherige Beispiel eine Operatorprozedur aufgerufen, wenn den Wert des berechnet `combinedSpan`.</xref:System.TimeSpan>  
  
 Ein Beispiel für das Aufrufen einer Operatorprozedur Unterhaltung, finden Sie unter [Gewusst wie: Verwenden einer Klasse, dass Operatoren definiert](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Achten Sie darauf, dass die Klasse oder Struktur, die Sie verwenden den Operator definiert, den Sie verwenden möchten.  
  
## <a name="see-also"></a>Siehe auch  
 [Operatorprozeduren](./operator-procedures.md)   
 [Gewusst wie: Definieren eines Operators](./how-to-define-an-operator.md)   
 [Gewusst wie: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md)   
 [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [Einschränkende](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
