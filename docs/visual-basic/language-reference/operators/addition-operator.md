---
title: + -Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
ms.openlocfilehash: da0c6f492b068c9caa50468ead47cdc08559bfce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576355"
---
# <a name="-operator-visual-basic"></a>+-Operator (Visual Basic)
Addiert zwei Zahlen ein, oder gibt den positiven Wert eines numerischen Ausdrucks zurück. Kann auch zum Verketten von zwei Ausdrücke verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```vb
expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`expression1`|Erforderlich. Jeder Ausdruck numerischen oder Zeichenfolgenausdruck.|  
|`expression2`|Erforderlich, wenn die `+` Operator einen negativen Wert berechnet. Jeder Ausdruck numerischen oder Zeichenfolgenausdruck.|  
  
## <a name="result"></a>Ergebnis  
 Wenn `expression1` und `expression2` sind beide numerisch ist, wird das Ergebnis ist ihre arithmetische Summe.  
  
 Wenn `expression2` nicht vorhanden ist, die `+` Operator ist der *unäre* Operator für die Identität für den unveränderten Wert eines Ausdrucks. In diesem Sinn der Vorgang besteht aus dem Beibehalten der Vorzeichen des `expression1`, sodass das Ergebnis negativ ist. wenn `expression1` ist negativ.  
  
 Wenn `expression1` und `expression2` sind Zeichenfolgen, das Ergebnis ist die Verkettung der entsprechenden Werte.  
  
 Wenn `expression1` und `expression2` sind gemischte Typen, die ausgeführte Aktion hängt ihre Typen, deren Inhalt und die Einstellung der [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md). Weitere Informationen finden Sie auf die Tabellen in "Hinweise".  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Alle numerischen Typen, einschließlich der Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`, und `String`.  
  
## <a name="remarks"></a>Hinweise  
 Im allgemeinen `+` führt eine arithmetische Addition möglichst und verkettet Sie nur, wenn beide Ausdrücke Zeichenfolgen sind.  
  
 Wenn kein Ausdruck ist ein `Object`, führt die folgenden Aktionen für Visual Basic.  
  
|Datentypen der Ausdrücke|Aktion des Compilers|  
|---|---|  
|Beide Ausdrücke sind numerische Datentypen (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, oder `Double`)|Fügen Sie hinzu. Der Ergebniswert vom Datentyp eines numerischen Typs, die für die Datentypen der entsprechenden `expression1` und `expression2`. Finden Sie in den Tabellen "Ganzzahlarithmetik" in [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Beide Ausdrücke sind vom Typ `String`|Verketten.|  
|Ein Ausdruck hat einen numerischen Datentyp aufweisen und die andere ist eine Zeichenfolge|Wenn `Option Strict` ist `On`, klicken Sie dann ein Compilerfehler generiert.<br /><br /> Wenn `Option Strict` ist `Off`, klicken Sie dann eine implizite Konvertierung der `String` zu `Double` und hinzufügen.<br /><br /> Wenn die `String` kann nicht konvertiert werden, um `Double`, lösen eine <xref:System.InvalidCastException> Ausnahme.|  
|Ein Ausdruck einen numerischen Datentyp aufweisen, und der andere ["Nothing"](../../../visual-basic/language-reference/nothing.md)|Hinzufügen, mit `Nothing` als 0 (null).|  
|Ein Ausdruck ist eine Zeichenfolge, und die andere ist `Nothing`|Verketten Sie ihn, mit `Nothing` Wert als "".|  
  
 Wenn ein Ausdruck ist ein `Object` Ausdruck ist, führt Visual Basic die folgenden Aktionen.  
  
|Datentypen der Ausdrücke|Aktion des Compilers|  
|---|---|  
|`Object` Ausdruck enthält einen numerischen Wert und der andere einen numerischen Datentyp|Wenn `Option Strict` ist `On`, klicken Sie dann ein Compilerfehler generiert.<br /><br /> Wenn `Option Strict` ist `Off`, fügen Sie dann hinzu.|  
|`Object` Ausdruck enthält einen numerischen Wert und der andere vom Typ `String`|Wenn `Option Strict` ist `On`, klicken Sie dann ein Compilerfehler generiert.<br /><br /> Wenn `Option Strict` ist `Off`, klicken Sie dann eine implizite Konvertierung der `String` zu `Double` und hinzufügen.<br /><br /> Wenn die `String` kann nicht konvertiert werden, um `Double`, lösen eine <xref:System.InvalidCastException> Ausnahme.|  
|`Object` Ausdruck enthält eine Zeichenfolge und der andere einen numerischen Datentyp|Wenn `Option Strict` ist `On`, klicken Sie dann ein Compilerfehler generiert.<br /><br /> Wenn `Option Strict` ist `Off`, konvertieren Sie die Zeichenfolge implizit `Object` zu `Double` und hinzufügen.<br /><br /> Wenn die Zeichenfolge `Object` kann nicht konvertiert werden, um `Double`, lösen eine <xref:System.InvalidCastException> Ausnahme.|  
|`Object` Ausdruck enthält eine Zeichenfolge und der andere vom Typ `String`|Wenn `Option Strict` ist `On`, klicken Sie dann ein Compilerfehler generiert.<br /><br /> Wenn `Option Strict` ist `Off`, klicken Sie dann eine implizite Konvertierung `Object` zu `String` dar und verkettet.|  
  
 Wenn beide Ausdrücke sind `Object` Ausdrücke, die Visual Basic führt die folgenden Aktionen (`Option Strict Off` nur).  
  
|Datentypen der Ausdrücke|Aktion des Compilers|  
|---|---|  
|Beide `Object` -Ausdrücke enthalten numerische Werte|Fügen Sie hinzu.|  
|Beide `Object` Ausdrücke sind vom Typ `String`|Verketten.|  
|Eine `Object` Ausdruck enthält einen numerischen Wert und die andere enthält eine Zeichenfolge|Die Zeichenfolge implizit konvertiert `Object` zu `Double` und hinzufügen.<br /><br /> Wenn die Zeichenfolge `Object` kann nicht in einen numerischen Wert konvertiert werden, und löst dann eine <xref:System.InvalidCastException> Ausnahme.|  
  
 Wenn entweder `Object` Ausdruck wird zu [nichts](../../../visual-basic/language-reference/nothing.md) oder <xref:System.DBNull>, `+` Operator behandelt es als ein `String` mit einem Wert von "".  
  
> [!NOTE]
>  Bei Verwendung der `+` Operator an, Sie möglicherweise nicht bestimmen, ob die Additions- oder Zeichenfolge Verkettung erfolgt. Verwenden der `&` Operator zum Verketten, um Mehrdeutigkeit zu vermeiden und um selbst dokumentierender Code bereitzustellen.  
  
## <a name="overloading"></a>Überladen  
 Die `+` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `+` Operator zum Addieren von Zahlen. Wenn die Operanden numerisch sind, berechnet Visual Basic das arithmetische Ergebnis. Das Ergebnis der arithmetische stellt die Summe der beiden Operanden dar.  
  
 [!code-vb[VbVbalrOperators#6](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_1.vb)]  
  
 Sie können auch die `+` Operator zum Verketten von Zeichenfolgen. Wenn die Operanden beide Zeichenfolgen sind, verkettet Visual Basic. Das Verkettungsergebnis stellt eine einzelne Zeichenfolge bestehend aus den Inhalt der beiden Operanden nach der anderen dar.  
  
 Wenn die Operanden unterschiedliche Typen sind, hängt das Ergebnis von der Einstellung von der [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md). Das folgende Beispiel zeigt das Ergebnis beim `Option Strict` ist `On`.  
  
 [!code-vb[VbVbalrOperators#53](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_2.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#51](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_4.vb)]  
  
 Das folgende Beispiel zeigt das Ergebnis beim `Option Strict` ist `Off`.  
  
 [!code-vb[VbVbalrOperators#54](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_5.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#52](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_6.vb)]  
  
 Um Mehrdeutigkeiten zu vermeiden, verwenden Sie die `&` Operator anstelle des `+` für die Verkettung.  
  
## <a name="see-also"></a>Siehe auch
- [&-Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [Verkettungsoperatoren](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
