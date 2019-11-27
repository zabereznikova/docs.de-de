---
title: '\-Operator'
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: 2b4cca99ed54195162530bb8eb950bd251bfbff9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347123"
---
# <a name="-operator-visual-basic"></a>\-Operator (Visual Basic)
Dividiert zwei Zahlen und gibt ein ganzzahliges Ergebnis zurück.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
expression1 \ expression2  
```  
  
## <a name="parts"></a>-Komponenten  
 `expression1`  
 Erforderlich Ein beliebiger numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich Ein beliebiger numerischer Ausdruck.  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Alle numerischen Typen, einschließlich der unsignierten und Gleit Komma Typen und `Decimal`.  
  
## <a name="result"></a>Ergebnis  
 Das Ergebnis ist der ganzzahlige Quotienten von `expression1` dividiert durch `expression2`, der jeden Rest verwirft und nur den ganzzahligen Teil beibehält. Dies wird als *Abschneiden*bezeichnet.  
  
 Der Ergebnis Datentyp ist ein numerischer Typ, der für die Datentypen von `expression1` und `expression2`geeignet ist. Weitere Informationen finden Sie in den Tabellen "ganzzahlige Arithmetik" unter [Datentypen von Operator Ergebnissen](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)  
  
 Der [Operator/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) gibt den vollständigen Quotienten zurück, der den Restwert im Bruch Teil beibehält.  
  
## <a name="remarks"></a>Hinweise  
 Vor der Durchführung der Division versucht Visual Basic, einen numerischen Gleit Komma Ausdruck in `Long`zu konvertieren. Wenn `Option Strict` `On`ist, tritt ein Compilerfehler auf. Wenn `Option Strict` `Off`ist, ist ein <xref:System.OverflowException> möglich, wenn der Wert außerhalb des Bereichs des [Long-Datentyps](../../../visual-basic/language-reference/data-types/long-data-type.md)liegt. Die Konvertierung in `Long` unterliegt auch der *Rundung von bankten*. Weitere Informationen finden Sie unter "Bruchteile" in den [Typkonvertierungs Funktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Wenn `expression1` oder `expression2` als " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet wird, wird es als 0 (null) behandelt.  
  
## <a name="attempted-division-by-zero"></a>Versuchte Division durch Null  
 Wenn `expression2` als NULL ausgewertet wird, löst der `\` Operator eine <xref:System.DivideByZeroException> Ausnahme aus. Dies gilt für alle numerischen Datentypen der Operanden.  
  
> [!NOTE]
> Der `\`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `\`-Operator verwendet, um eine ganzzahlige Division auszuführen. Das Ergebnis ist eine ganze Zahl, die den ganzzahligen Quotienten der beiden Operanden darstellt, wobei der restliche Rest verworfen wird.  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 Die Ausdrücke im vorherigen Beispiel geben Werte von 2, 3, 33 bzw.-22 zurück.  
  
## <a name="see-also"></a>Siehe auch

- [\\=-Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [Operator/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
