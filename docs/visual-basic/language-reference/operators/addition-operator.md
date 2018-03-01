---
title: + Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fb0d66db2d777c046ccec69acc1f2069d21baf6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>+-Operator (Visual Basic)
Addiert zwei Zahlen oder gibt den positiven Wert eines numerischen Ausdrucks zurück. Kann auch zum Verketten zweier Zeichenfolgenausdrücke verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
      expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`expression1`|Erforderlich. Ein beliebiger Ausdruck numerischen oder Zeichenfolgenausdruck.|  
|`expression2`|Erforderlich, es sei denn, die `+` Operator einen negativen Wert berechnet wird. Ein beliebiger Ausdruck numerischen oder Zeichenfolgenausdruck.|  
  
## <a name="result"></a>Ergebnis  
 Wenn `expression1` und `expression2` sind beide numerisch ist, wird das Ergebnis wird der arithmetische Summe.  
  
 Wenn `expression2` nicht vorhanden ist, die `+` Operator ist der *unäre* Identitätsoperator für den unveränderten Wert eines Ausdrucks. In diesem Sinn der Vorgang besteht aus dem Beibehalten der Vorzeichens des `expression1`, sodass das Ergebnis negativ ist. wenn `expression1` ist ein negativer Wert.  
  
 Wenn `expression1` und `expression2` sind Zeichenfolgen, das Ergebnis ist die Verkettung der entsprechenden Werte.  
  
 Wenn `expression1` und `expression2` sind gemischte Datentypen, welche Aktion hängt von ihrer Typen, deren Inhalt und die Einstellung von der [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md). Weitere Informationen finden Sie in den Tabellen in "Hinweise".  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Alle numerischen Typen, einschließlich der Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`, und `String`.  
  
## <a name="remarks"></a>Hinweise  
 Im allgemeinen `+` arithmetische Addition möglichst ausführt und nur, wenn beide Ausdrücke Zeichenfolgen sind verkettet.  
  
 Wenn kein Ausdruck ist ein `Object`, Visual Basic führt die folgenden Aktionen aus.  
  
|Datentypen von Ausdrücken|Aktion des Compilers|  
|---|---|  
|Beide Ausdrücke sind numerische Datentypen (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, oder `Double`)|Fügen Sie hinzu. Datentyp des Ergebnisses ist ein numerischer Typ für die Datentypen der entsprechenden `expression1` und `expression2`. Finden Sie in den Tabellen "Ganzzahlarithmetik" in [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Beide Ausdrücke sind vom Typ`String`|Verketten.|  
|Ein Ausdruck hat einen numerischen Datentyp aufweisen und das andere ist eine Zeichenfolge|Wenn `Option Strict` ist `On`, klicken Sie dann ein Compilerfehler generiert.<br /><br /> Wenn `Option Strict` ist `Off`, dann implizit konvertieren die `String` auf `Double` und hinzufügen.<br /><br /> Wenn die `String` kann nicht konvertiert werden, um `Double`, lösen Sie eine <xref:System.InvalidCastException> Ausnahme.|  
|Ein Ausdruck hat einen numerischen Datentyp aufweisen, und der andere [nichts](../../../visual-basic/language-reference/nothing.md)|Hinzufügen, mit `Nothing` als 0 (null).|  
|Ein Ausdruck ist eine Zeichenfolge, und das andere ist`Nothing`|Verketten, mit `Nothing` Wert als "".|  
  
 Wenn ein Ausdruck ist ein `Object` Ausdruck, Visual Basic werden folgende Aktionen ausgeführt.  
  
|Datentypen von Ausdrücken|Aktion des Compilers|  
|---|---|  
|`Object`Ausdruck enthält einen numerischen Wert und der andere einen numerischen Datentyp|Wenn `Option Strict` ist `On`, klicken Sie dann ein Compilerfehler generiert.<br /><br /> Wenn `Option Strict` ist `Off`, klicken Sie dann auf Hinzufügen.|  
|`Object`Ausdruck enthält einen numerischen Wert und der andere vom Typ`String`|Wenn `Option Strict` ist `On`, klicken Sie dann ein Compilerfehler generiert.<br /><br /> Wenn `Option Strict` ist `Off`, dann implizit konvertieren die `String` auf `Double` und hinzufügen.<br /><br /> Wenn die `String` kann nicht konvertiert werden, um `Double`, lösen Sie eine <xref:System.InvalidCastException> Ausnahme.|  
|`Object`Ausdruck enthält eine Zeichenfolge und der andere einen numerischen Datentyp|Wenn `Option Strict` ist `On`, klicken Sie dann ein Compilerfehler generiert.<br /><br /> Wenn `Option Strict` ist `Off`, konvertieren Sie die Zeichenfolge implizit `Object` auf `Double` und hinzufügen.<br /><br /> Wenn die Zeichenfolge `Object` kann nicht konvertiert werden, um `Double`, lösen Sie eine <xref:System.InvalidCastException> Ausnahme.|  
|`Object`Ausdruck enthält eine Zeichenfolge und der andere vom Typ`String`|Wenn `Option Strict` ist `On`, klicken Sie dann ein Compilerfehler generiert.<br /><br /> Wenn `Option Strict` ist `Off`, dann implizit konvertieren `Object` auf `String` und verkettet.|  
  
 Wenn beide Ausdrücke `Object` Ausdrücke, Visual Basic werden folgende Aktionen ausgeführt (`Option Strict Off` nur).  
  
|Datentypen von Ausdrücken|Aktion des Compilers|  
|---|---|  
|Beide `Object` -Ausdrücke enthalten numerische Werte|Fügen Sie hinzu.|  
|Beide `Object` Ausdrücke sind vom Typ`String`|Verketten.|  
|Ein `Object` Ausdruck enthält einen numerischen Wert und die andere enthält eine Zeichenfolge|Konvertieren Sie die Zeichenfolge implizit `Object` auf `Double` und hinzufügen.<br /><br /> Wenn die Zeichenfolge `Object` kann nicht in einen numerischen Wert konvertiert werden, und löst eine <xref:System.InvalidCastException> Ausnahme.|  
  
 Wenn entweder `Object` Ausdruck wird zu [nichts](../../../visual-basic/language-reference/nothing.md) oder <xref:System.DBNull>, `+` Operator behandelt sie als eine `String` mit einem Wert von "".  
  
> [!NOTE]
>  Bei Verwendung der `+` -Operator, Sie möglicherweise nicht zu bestimmen, ob die Addition oder Zeichenfolge Verkettung erfolgt. Verwenden der `&` Operator zum Verketten, um Mehrdeutigkeit zu vermeiden und sich selbst dokumentierenden Code bereitzustellen.  
  
## <a name="overloading"></a>Überladen  
 Die `+` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `+` Operator, um Zahlen zu addieren. Wenn die Operanden numerisch sind, berechnet Visual Basic das arithmetische Ergebnis. Das arithmetische Ergebnis stellt die Summe der beiden Operanden dar.  
  
 [!code-vb[VbVbalrOperators#6](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_1.vb)]  
  
 Sie können auch die `+` Operator zum Verketten von Zeichenfolgen. Wenn die Operanden beide Zeichenfolgen sind, verkettet Visual Basic. Das Verkettungsergebnis stellt eine einzelne Zeichenfolge, die den Inhalt der beiden Operanden nach der anderen besteht.  
  
 Wenn die Operanden unterschiedliche Typen sind, hängt das Ergebnis von der Einstellung der [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md). Das folgende Beispiel veranschaulicht das Ergebnis beim `Option Strict` ist `On`.  
  
 [!code-vb[VbVbalrOperators#53](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_2.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#51](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_4.vb)]  
  
 Das folgende Beispiel veranschaulicht das Ergebnis beim `Option Strict` ist `Off`.  
  
 [!code-vb[VbVbalrOperators#54](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_5.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#52](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_6.vb)]  
  
 Um Mehrdeutigkeit zu umgehen, verwenden Sie die `&` Operator anstelle von `+` zum Verketten.  
  
## <a name="see-also"></a>Siehe auch  
 [&-Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [Verkettungsoperatoren](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
