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
ms.openlocfilehash: 1f8095afc5f096928b946607adc715af49827022
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370881"
---
# <a name="-operator-visual-basic"></a>\-Operator (Visual Basic)
Dividiert zwei Zahlen und gibt eine ganze Zahl als Ergebnis zurück.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
expression1 \ expression2  
```  
  
## <a name="parts"></a>Bestandteile  
 `expression1`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Alle numerischen Typen, einschließlich der nicht signierten-und Gleit Komma Typen und `Decimal` .  
  
## <a name="result"></a>Ergebnis  
 Das Ergebnis ist der ganzzahlige Quotienten von `expression1` dividiert durch `expression2` , der jeden Rest verwirft und nur den ganzzahligen Teil beibehält. Dies wird als *Abschneiden*bezeichnet.  
  
 Der Ergebnis Datentyp ist ein numerischer Typ, der für die Datentypen von und geeignet ist `expression1` `expression2` . Weitere Informationen finden Sie in den Tabellen "ganzzahlige Arithmetik" unter [Datentypen von Operator Ergebnissen](data-types-of-operator-results.md)  
  
 Der [Operator/(Visual Basic)](floating-point-division-operator.md) gibt den vollständigen Quotienten zurück, der den Restwert im Bruch Teil beibehält.  
  
## <a name="remarks"></a>Bemerkungen  
 Vor der Durchführung der Division versucht Visual Basic, den numerischen Gleit Komma Ausdruck in zu konvertieren `Long` . Wenn den Wert `Option Strict` `On` hat, tritt ein Compilerfehler auf. Wenn `Option Strict` `Off` <xref:System.OverflowException> den Wert hat, ist ein möglich, wenn der Wert außerhalb des Bereichs des Long- [Datentyps](../data-types/long-data-type.md)liegt. Die Konvertierung in `Long` unterliegt auch der *-Rundung des Bankers*. Weitere Informationen finden Sie unter "Bruchteile" in den [Typkonvertierungs Funktionen](../functions/type-conversion-functions.md).  
  
 Wenn `expression1` oder `expression2` als " [Nothing](../nothing.md)" ausgewertet wird, wird es als 0 (null) behandelt.  
  
## <a name="attempted-division-by-zero"></a>Versuchte Division durch Null  
 Wenn `expression2` null ergibt, löst der `\` Operator eine- <xref:System.DivideByZeroException> Ausnahme aus. Dies gilt für alle numerischen Datentypen der Operanden.  
  
> [!NOTE]
> Der `\` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der-Operator verwendet, um eine ganz Zahl `\` Division auszuführen. Das Ergebnis ist eine ganze Zahl, die den ganzzahligen Quotienten der beiden Operanden darstellt, wobei der restliche Rest verworfen wird.  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 Die Ausdrücke im vorherigen Beispiel geben Werte von 2, 3, 33 bzw.-22 zurück.  
  
## <a name="see-also"></a>Weitere Informationen

- [\\=-Operator](integer-division-assignment-operator.md)
- [Operator/(Visual Basic)](floating-point-division-operator.md)
- [Option Strict-Anweisung](../statements/option-strict-statement.md)
- [Arithmetische Operatoren](arithmetic-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
