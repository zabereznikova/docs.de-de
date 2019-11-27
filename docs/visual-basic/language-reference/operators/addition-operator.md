---
title: + Operator
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
ms.openlocfilehash: 12c14b3be0562a31470ddbd2d5489ccdbdf3b62b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350296"
---
# <a name="-operator-visual-basic"></a>+-Operator (Visual Basic)
Addiert zwei Zahlen oder gibt den positiven Wert eines numerischen Ausdrucks zurück. Kann auch verwendet werden, um zwei Zeichen folgen Ausdrücke zu verketten.  
  
## <a name="syntax"></a>Syntax  
  
```vb
expression1 + expression2
```
  
oder

```vb  
+expression1  
```  
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`expression1`|Erforderlich Beliebiger numerischer Ausdruck oder Zeichen folgen Ausdruck.|  
|`expression2`|Erforderlich, es sei denn, der `+`-Operator berechnet einen negativen Wert. Beliebiger numerischer Ausdruck oder Zeichen folgen Ausdruck.|  
  
## <a name="result"></a>Ergebnis  
 Wenn `expression1` und `expression2` beide numerisch sind, ist das Ergebnis die arithmetische Summe.  
  
 Wenn `expression2` nicht vorhanden ist, ist der `+` Operator der unäre Identitäts Operator für den *unveränderten* Wert eines Ausdrucks. In diesem Sinne besteht der Vorgang darin, das Vorzeichen `expression1`beizubehalten, sodass das Ergebnis negativ ist, wenn `expression1` negativ ist.  
  
 Wenn `expression1` und `expression2` beide Zeichen folgen sind, ist das Ergebnis die Verkettung ihrer Werte.  
  
 Wenn `expression1` und `expression2` gemischte Typen sind, hängt die ausgeführte Aktion von ihren Typen, ihrem Inhalt und der Einstellung der [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)ab. Weitere Informationen finden Sie in den Tabellen unter "Hinweise".  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Alle numerischen Typen, einschließlich der unsignierten und Gleit Komma Typen und der `Decimal`, und `String`.  
  
## <a name="remarks"></a>Hinweise  
 Im Allgemeinen führt `+` nach Möglichkeit eine arithmetische Addition durch und verkettet nur, wenn beide Ausdrücke Zeichen folgen sind.  
  
 Wenn keiner der Ausdrücke eine `Object`ist, führt Visual Basic die folgenden Aktionen aus.  
  
|Datentypen von Ausdrücken|Aktion nach Compiler|  
|---|---|  
|Beide Ausdrücke sind numerische Datentypen (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`oder `Double`).|Hinzufügen. Der Ergebnis Datentyp ist ein numerischer Typ, der für die Datentypen von `expression1` und `expression2`geeignet ist. Weitere Informationen finden Sie in den Tabellen "ganzzahlige Arithmetik" unter [Datentypen von Operator Ergebnissen](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)|  
|Beide Ausdrücke sind vom Typ `String`|Verketten.|  
|Ein Ausdruck ist ein numerischer Datentyp, der andere eine Zeichenfolge.|Wenn `Option Strict` `On`ist, generieren Sie einen Compilerfehler.<br /><br /> Wenn `Option Strict` `Off`ist, konvertieren Sie den `String` implizit in `Double`, und fügen Sie hinzu.<br /><br /> Wenn die `String` nicht in `Double`konvertiert werden kann, lösen Sie eine <xref:System.InvalidCastException> Ausnahme aus.|  
|Ein Ausdruck ist ein numerischer Datentyp, der andere ist [Nothing](../../../visual-basic/language-reference/nothing.md) .|Fügen Sie hinzu, wobei `Nothing` den Wert NULL hat.|  
|Ein Ausdruck ist eine Zeichenfolge, und die andere ist `Nothing`|Concatenate, wobei `Nothing` den Wert "" hat.|  
  
 Wenn ein Ausdruck ein `Object` Ausdruck ist, führt Visual Basic die folgenden Aktionen aus.  
  
|Datentypen von Ausdrücken|Aktion nach Compiler|  
|---|---|  
|`Object` Ausdruck enthält einen numerischen Wert und der andere einen numerischen Datentyp.|Wenn `Option Strict` `On`ist, generieren Sie einen Compilerfehler.<br /><br /> Wenn `Option Strict` `Off`ist, fügen Sie hinzu.|  
|`Object` Ausdruck enthält einen numerischen Wert, der andere vom Typ `String`|Wenn `Option Strict` `On`ist, generieren Sie einen Compilerfehler.<br /><br /> Wenn `Option Strict` `Off`ist, konvertieren Sie den `String` implizit in `Double`, und fügen Sie hinzu.<br /><br /> Wenn die `String` nicht in `Double`konvertiert werden kann, lösen Sie eine <xref:System.InvalidCastException> Ausnahme aus.|  
|`Object` Ausdruck enthält eine Zeichenfolge und die andere einen numerischen Datentyp.|Wenn `Option Strict` `On`ist, generieren Sie einen Compilerfehler.<br /><br /> Wenn `Option Strict` `Off`ist, konvertieren Sie die Zeichen folgen `Object` implizit in `Double`, und fügen Sie hinzu.<br /><br /> Wenn die Zeichenfolge `Object` nicht in `Double`konvertiert werden kann, lösen Sie eine <xref:System.InvalidCastException> Ausnahme aus.|  
|`Object` Ausdruck enthält eine Zeichenfolge, und die andere weist den Typ auf `String`|Wenn `Option Strict` `On`ist, generieren Sie einen Compilerfehler.<br /><br /> Wenn `Option Strict` `Off`ist, konvertieren Sie `Object` implizit in `String` und verketten.|  
  
 Wenn beide Ausdrücke `Object` Ausdrücke sind, führt Visual Basic die folgenden Aktionen aus (nur`Option Strict Off`).  
  
|Datentypen von Ausdrücken|Aktion nach Compiler|  
|---|---|  
|Beide `Object` Ausdrücke enthalten numerische Werte.|Hinzufügen.|  
|Beide `Object` Ausdrücke sind vom Typ `String`|Verketten.|  
|Ein `Object` Ausdruck enthält einen numerischen Wert, der andere eine Zeichenfolge.|Konvertieren Sie die Zeichenfolge `Object` implizit in `Double`, und fügen Sie hinzu.<br /><br /> Wenn die Zeichenfolge `Object` nicht in einen numerischen Wert konvertiert werden kann, lösen Sie eine <xref:System.InvalidCastException>-Ausnahme aus.|  
  
 Wenn `Object` Ausdruck entweder " [Nothing](../../../visual-basic/language-reference/nothing.md) " oder "<xref:System.DBNull>" ergibt, behandelt der `+`-Operator ihn als `String` mit dem Wert "".  
  
> [!NOTE]
> Wenn Sie den `+`-Operator verwenden, sind Sie möglicherweise nicht in der Lage, zu bestimmen, ob Addition oder Zeichen folgen Verkettung stattfinden. Verwenden Sie den `&`-Operator für die Verkettung, um Mehrdeutigkeit zu vermeiden und selbst dokumentierenden Code bereitzustellen.  
  
## <a name="overloading"></a>Überladen  
 Der `+`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `+`-Operator verwendet, um Zahlen hinzuzufügen. Wenn die Operanden beide numerisch sind, berechnet Visual Basic das arithmetische Ergebnis. Das arithmetische Ergebnis stellt die Summe der beiden Operanden dar.  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 Sie können auch den `+`-Operator verwenden, um Zeichen folgen zu verketten. Wenn die Operanden beide Zeichen folgen sind, werden Sie von Visual Basic verkettet. Das Verkettungs Ergebnis stellt eine einzelne Zeichenfolge dar, die aus dem Inhalt der beiden Operanden nacheinander besteht.  
  
 Wenn es sich bei den Operanden um gemischte Typen handelt, hängt das Ergebnis von der Einstellung der [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)ab. Das folgende Beispiel veranschaulicht das Ergebnis, wenn `Option Strict` `On`ist.  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 Das folgende Beispiel veranschaulicht das Ergebnis, wenn `Option Strict` `Off`ist.  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 Um Mehrdeutigkeit auszuschließen, sollten Sie den `&`-Operator anstelle von `+` für die Verkettung verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [&-Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [Verkettungsoperatoren](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
