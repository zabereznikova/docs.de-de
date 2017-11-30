---
title: '&amp;Operator (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76c8fc52a518dfe7850a5680b7d4f06f3d09bf73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-visual-basic"></a>&amp;Operator (Visual Basic)
Generiert eine zeichenfolgenverkettung aus zwei Ausdrücken.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Alle `String` oder `Object` Variable.  
  
 `expression1`  
 Erforderlich. Jeder Ausdruck mit einem Datentyp, der erweitert `String`.  
  
 `expression2`  
 Erforderlich. Jeder Ausdruck mit einem Datentyp, der erweitert `String`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Datentyp des `expression1` oder `expression2` ist nicht `String` jedoch erweitert wird, um `String`, wird es in konvertiert `String`. Wenn entweder der Datentypen wird nicht erweitert werden, um `String`, generiert der Compiler einen Fehler.  
  
 Der Datentyp des `result` ist `String`. Wenn einer oder beide Ausdrücke [nichts](../../../visual-basic/language-reference/nothing.md) oder einen Wert von <xref:System.DBNull.Value?displayProperty=nameWithType>, werden sie behandelt, als eine Zeichenfolge mit dem Wert "".  
  
> [!NOTE]
>  Die `&` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
>  Das kaufmännische und-Zeichen (&) können auch zum Identifizieren von Variablen als Typ verwendet werden `Long`. Weitere Informationen finden Sie unter [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `&` Operator zum Verketten von Zeichenfolgen zu erzwingen. Das Ergebnis ist ein Zeichenfolgenwert, der die Verkettung von den beiden Zeichenfolgenoperanden darstellt.  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [&=-Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [Verkettungsoperatoren](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Verkettungsoperatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
