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
ms.openlocfilehash: bc31e4c66c64d891e3fffd809b7ae99b9c9a0520
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873460"
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
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`expression1`|Erforderlich. Beliebiger numerischer Ausdruck oder Zeichen folgen Ausdruck.|  
|`expression2`|Erforderlich, es sei denn, der `+` Operator berechnet einen negativen Wert. Beliebiger numerischer Ausdruck oder Zeichen folgen Ausdruck.|  
  
## <a name="result"></a>Ergebnis  

 Wenn `expression1` und `expression2` beide numerisch sind, entspricht das Ergebnis Ihrer arithmetischen Summe.  
  
 Wenn `expression2` nicht vorhanden ist, `+` ist der Operator der *unäre* Identitäts Operator für den unveränderten Wert eines Ausdrucks. In diesem Sinne besteht der Vorgang darin, das Vorzeichen von beizubehalten `expression1` , sodass das Ergebnis negativ ist, wenn `expression1` negativ ist.  
  
 Wenn `expression1` und `expression2` beide Zeichen folgen sind, ist das Ergebnis die Verkettung ihrer Werte.  
  
 Wenn `expression1` und `expression2` gemischte Typen sind, hängt die ausgeführte Aktion von ihren Typen, ihrem Inhalt und der Einstellung der [Option Strict-Anweisung](../statements/option-strict-statement.md)ab. Weitere Informationen finden Sie in den Tabellen unter "Hinweise".  
  
## <a name="supported-types"></a>Unterstützte Typen  

 Alle numerischen Typen, einschließlich der unsignierten-und Gleit Komma Typen und `Decimal` , und `String` .  
  
## <a name="remarks"></a>Bemerkungen  

 Im allgemeinen `+` führt eine arithmetische Addition aus, wenn dies möglich ist, und verkettet nur, wenn beide Ausdrücke Zeichen folgen sind.  
  
 Wenn keiner der Ausdrücke eine ist `Object` , führt Visual Basic die folgenden Aktionen aus.  
  
|Datentypen von Ausdrücken|Aktion nach Compiler|  
|---|---|  
|Beide Ausdrücke sind numerische Datentypen ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` , `ULong` , `Decimal` , `Single` oder `Double` ).|Hinzufügen Der Ergebnis Datentyp ist ein numerischer Typ, der für die Datentypen von und geeignet ist `expression1` `expression2` . Weitere Informationen finden Sie in den Tabellen "ganzzahlige Arithmetik" unter [Datentypen von Operator Ergebnissen](data-types-of-operator-results.md)|  
|Beide Ausdrücke sind vom Typ. `String`|Verketten.|  
|Ein Ausdruck ist ein numerischer Datentyp, der andere eine Zeichenfolge.|Wenn den Wert `Option Strict` `On` hat, generieren Sie einen Compilerfehler.<br /><br /> Wenn `Option Strict` `Off` den Wert hat, konvertieren Sie den implizit `String` in, `Double` und fügen Sie hinzu.<br /><br /> Wenn `String` nicht in konvertiert werden kann `Double` , wird eine <xref:System.InvalidCastException> Ausnahme ausgelöst.|  
|Ein Ausdruck ist ein numerischer Datentyp, der andere ist [Nothing](../nothing.md) .|Fügen Sie mit einem Wert von 0 (null) hinzu `Nothing` .|  
|Ein Ausdruck ist eine Zeichenfolge, und die andere ist. `Nothing`|Concatenate mit dem `Nothing` Wert "".|  
  
 Wenn ein Ausdruck ein `Object` Ausdruck ist, führt Visual Basic die folgenden Aktionen aus.  
  
|Datentypen von Ausdrücken|Aktion nach Compiler|  
|---|---|  
|`Object` der Ausdruck enthält einen numerischen Wert und der andere einen numerischen Datentyp.|Wenn den Wert `Option Strict` `On` hat, generieren Sie einen Compilerfehler.<br /><br /> Wenn `Option Strict` ist `Off` , dann hinzufügen.|  
|`Object` der Ausdruck enthält einen numerischen Wert, der andere vom Typ. `String`|Wenn den Wert `Option Strict` `On` hat, generieren Sie einen Compilerfehler.<br /><br /> Wenn `Option Strict` `Off` den Wert hat, konvertieren Sie den implizit `String` in, `Double` und fügen Sie hinzu.<br /><br /> Wenn `String` nicht in konvertiert werden kann `Double` , wird eine <xref:System.InvalidCastException> Ausnahme ausgelöst.|  
|`Object` der Ausdruck enthält eine Zeichenfolge, die andere einen numerischen Datentyp.|Wenn den Wert `Option Strict` `On` hat, generieren Sie einen Compilerfehler.<br /><br /> Wenn `Option Strict` ist `Off` , konvertieren Sie die Zeichenfolge implizit `Object` in, `Double` und fügen Sie hinzu.<br /><br /> Wenn die Zeichenfolge `Object` nicht in konvertiert werden kann `Double` , wird eine <xref:System.InvalidCastException> Ausnahme ausgelöst.|  
|`Object` der Ausdruck enthält eine Zeichenfolge, und die andere weist den Typ auf. `String`|Wenn den Wert `Option Strict` `On` hat, generieren Sie einen Compilerfehler.<br /><br /> Wenn `Option Strict` `Off` den Wert hat, wird implizit `Object` in konvertiert `String` und verkettet.|  
  
 Wenn beide Ausdrücke `Object` Ausdrücke sind, Visual Basic die folgenden Aktionen durchführt ( `Option Strict Off` nur).  
  
|Datentypen von Ausdrücken|Aktion nach Compiler|  
|---|---|  
|Beide `Object` Ausdrücke enthalten numerische Werte.|Hinzufügen|  
|Beide `Object` Ausdrücke sind vom Typ. `String`|Verketten.|  
|Ein `Object` Ausdruck enthält einen numerischen Wert, während der andere eine Zeichenfolge enthält.|Konvertieren Sie die Zeichenfolge implizit `Object` in `Double` und fügen Sie hinzu.<br /><br /> Wenn die Zeichenfolge `Object` nicht in einen numerischen Wert konvertiert werden kann, wird eine <xref:System.InvalidCastException> Ausnahme ausgelöst.|  
  
 Wenn `Object` einer der Ausdrücke als " [Nothing](../nothing.md) " oder ausgewertet <xref:System.DBNull> wird, `+` behandelt der Operator ihn als `String` mit dem Wert "".  
  
> [!NOTE]
> Wenn Sie den- `+` Operator verwenden, sind Sie möglicherweise nicht in der Lage, zu bestimmen, ob Addition oder Zeichen folgen Verkettung auftreten. Verwenden `&` Sie den Operator für die Verkettung, um Mehrdeutigkeit zu vermeiden und selbst dokumentierenden Code bereitzustellen.  
  
## <a name="overloading"></a>Überladen  

 Der `+` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird der- `+` Operator verwendet, um Zahlen hinzuzufügen. Wenn die Operanden beide numerisch sind, berechnet Visual Basic das arithmetische Ergebnis. Das arithmetische Ergebnis stellt die Summe der beiden Operanden dar.  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 Sie können auch den- `+` Operator verwenden, um Zeichen folgen zu verketten. Wenn die Operanden beide Zeichen folgen sind, werden Sie von Visual Basic verkettet. Das Verkettungs Ergebnis stellt eine einzelne Zeichenfolge dar, die aus dem Inhalt der beiden Operanden nacheinander besteht.  
  
 Wenn es sich bei den Operanden um gemischte Typen handelt, hängt das Ergebnis von der Einstellung der [Option Strict-Anweisung](../statements/option-strict-statement.md)ab. Das folgende Beispiel veranschaulicht das Ergebnis, wenn `Option Strict` ist `On` .  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 Das folgende Beispiel veranschaulicht das Ergebnis, wenn `Option Strict` ist `Off` .  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 Um Mehrdeutigkeit auszuschließen, verwenden Sie den- `&` Operator anstelle von `+` für die Verkettung.  
  
## <a name="see-also"></a>Weitere Informationen

- [&-Operator](concatenation-operator.md)
- [Verkettungsoperatoren](concatenation-operators.md)
- [Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Arithmetische Operatoren in Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Option Strict-Anweisung](../statements/option-strict-statement.md)
