---
title: Operator Mod(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5464b57c993e5703c09529b527a7bc714e045870
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mod-operator-visual-basic"></a>Operator Mod(Visual Basic)
Dividiert zwei Zahlen und gibt nur den Restwert zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a>Teile  
 `number1`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
 `number2`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Alle numerischen Typen. Dazu gehören auch die Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.  
  
## <a name="result"></a>Ergebnis  
 Das Ergebnis wird im weiteren Verlauf nach `number1` wird geteilt durch `number2`. Z. B. der Ausdruck `14 Mod 4` 2 ergibt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn entweder `number1` oder `number2` ist der Wert ein Gleitkommazahl der Gleitkommarest der Division wird zurückgegeben. Der Datentyp des Ergebnisses ist der kleinste Datentyp, die alle möglichen Werte enthalten kann, die aus der Division mit den Datentypen der resultieren `number1` und `number2`.  
  
 Wenn `number1` oder `number2` ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird dies als 0 (null) behandelt.  
  
 Verwandte Operatoren umfassen Folgendes:  
  
-   Die [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) gibt den ganzzahligen Quotienten einer Division zurück. Z. B. der Ausdruck `14 \ 4` 3 ergibt.  
  
-   Die [/-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) gibt den vollständigen Quotienten, einschließlich des Restes, als Gleitkommazahl zurück. Z. B. der Ausdruck `14 / 4` 3.5 ergibt.  
  
## <a name="attempted-division-by-zero"></a>Versuchte Division durch 0 (null)  
 Wenn `number2` ergibt 0 (null), das Verhalten der `Mod` Operator hängt von den Datentyp des Operanden. Ganzzahldivision wird eine <xref:System.DivideByZeroException> Ausnahme. Gibt eine Gleitkommadivision <xref:System.Double.NaN>.  
  
## <a name="equivalent-formula"></a>Entsprechende Formel  
 Der Ausdruck `a Mod b` ist gleichbedeutend mit beiden der folgenden Formeln:  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a>Gleitkomma Ungenauigkeit  
 Wenn Sie mit Gleitkommazahlen arbeiten, denken Sie daran, dass sie nicht immer eine genaue Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen führen, über bestimmte Vorgänge, z. B. Wertvergleich und `Mod` Operator. Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="overloading"></a>Überladen  
 Die `Mod` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann. Wenn Ihr Code wendet `Mod` mit einer Instanz einer Klasse oder Struktur, die eine Überladung verwendet wird, werden Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Mod` Operator, um zwei Zahlen dividiert, und geben Sie nur den Restwert zurück. Wenn entweder eine Gleitkommazahl ist, ist das Ergebnis eine Gleitkommazahl, die den Rest darstellt.  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die potenzielle Ungenauigkeit der Gleitkomma-Operanden. In der ersten Anweisung den Operanden sind `Double`, und 0,2 ist ein unendlicher Binärbruch mit dem gespeicherten Wert 0,20000000000000001. In der zweiten Anweisung wird das Literal-Typzeichen `D` erzwingt, dass beide Operanden `Decimal`, und 0,2 verfügt über eine genaue Darstellung.  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
