---
title: '- Operator (Visual Basic) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Negate
- vb.-
dev_langs:
- VB
helpviewer_keywords:
- '- operator [Visual Basic]'
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator
- operators [Visual Basic], arithmetic
- subtraction operator, syntax
- arithmetic operators, subtraction
- difference operator
- math operators
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
caps.latest.revision: 14
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
ms.openlocfilehash: 7f45094da7bc61687d9c767d25858aa214bf1978
ms.lasthandoff: 03/13/2017

---
# <a name="--operator-visual-basic"></a>--Operator (Visual Basic)
Gibt die Differenz zwischen zwei numerischen Ausdrücken oder den negativen Wert eines numerischen Ausdrucks zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a>Teile  
 `expression1`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich, wenn die `–` Operator einen negativen Wert berechnet. Ein beliebiger numerischer Ausdruck.  
  
## <a name="result"></a>Ergebnis  
 Das Ergebnis ist der Unterschied zwischen `expression1` und `expression2`, oder der negierte Wert der `expression1`.  
  
 Datentyp des Ergebnisses ist eine für die Datentypen der numerischen Typ `expression1` und `expression2`. Finden Sie in den Tabellen "Ganzzahlarithmetik" in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Alle numerischen Typen. Dies schließt die Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.  
  
## <a name="remarks"></a>Hinweise  
 Im ersten Anwendungsbeispiel in der zuvor gezeigten Syntax der `–` -Operator ist der *binäre* arithmetische Subtraktionsoperator für die Differenz zwischen zwei numerischen Ausdrücken.  
  
 Im zweiten Anwendungsbeispiel in der zuvor gezeigten Syntax der `–` -Operator ist der *unäre* Negationsoperator für den negativen Wert eines Ausdrucks. In diesem Sinne Negation Umkehrung des Vorzeichens von besteht aus `expression1` , damit das Ergebnis positiv ist Wenn `expression1` ist negativ.  
  
 Wenn die beiden Ausdrücke ist [nichts](../../../visual-basic/language-reference/nothing.md)der `–` Operator wird er als&0; (null) behandelt.  
  
> [!NOTE]
>  Die `–` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur aufweist. Wenn Ihr Code auf eine solche Klasse oder Struktur dieser Operator verwendet wird, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `–` Operator berechnet und die Differenz zwischen zwei Zahlen zurückgibt und anschließend eine Zahl zu negieren.  
  
 [!code-vb[VbVbalrOperators&#10;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 Nach der Ausführung dieser Anweisungen `binaryResult` enthält 124.45 und `unaryResult` –334.90 enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [-=-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
 [arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operatorrangfolge in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)

