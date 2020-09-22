---
title: '* Operator'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: 7038fef4258d190b726a851b26f2a2840ff3c0ea
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873368"
---
# <a name="-operator-visual-basic"></a>*-Operator (Visual Basic)

Multipliziert zwei Zahlen.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`number1`|Erforderlich. Ein beliebiger numerischer Ausdruck.|  
|`number2`|Erforderlich. Ein beliebiger numerischer Ausdruck.|  
  
## <a name="result"></a>Ergebnis  

 Das Ergebnis ist das Produkt von `number1` und `number2` .  
  
## <a name="supported-types"></a>Unterstützte Typen  

 Alle numerischen Typen, einschließlich der nicht signierten-und Gleit Komma Typen und `Decimal` .  
  
## <a name="remarks"></a>Bemerkungen  

 Der Datentyp des Ergebnisses hängt von den Typen der Operanden ab. In der folgenden Tabelle wird gezeigt, wie der Datentyp des Ergebnisses bestimmt wird.  
  
|Operanden Datentypen|Ergebnis Datentyp|  
|---|---|  
|Beide Ausdrücke sind [ganzzahlige](../data-types/uinteger-data-type.md)Datentypen ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), UInteger, [Long](../data-types/long-data-type.md), [ulong](../data-types/ulong-data-type.md)).|Ein numerischer Datentyp, der für die Datentypen von und geeignet ist `number1` `number2` . Weitere Informationen finden Sie in den Tabellen "ganzzahlige Arithmetik" unter [Datentypen von Operator Ergebnissen](data-types-of-operator-results.md)|  
|Beide Ausdrücke sind [Decimal](../data-types/decimal-data-type.md) .|`Decimal`|  
|Beide Ausdrücke sind [Single](../data-types/single-data-type.md)|`Single`|  
|Jeder Ausdruck ist ein Gleit Komma Datentyp ( `Single` oder [Double](../data-types/double-data-type.md)), aber nicht beides `Single` (Beachten Sie, dass `Decimal` es sich nicht um einen Gleit Komma Datentyp handelt).|`Double`|  
  
 Wenn ein Ausdruck zu " [Nothing](../nothing.md)" ausgewertet wird, wird er als 0 (null) behandelt.  
  
## <a name="overloading"></a>Überladen  

 Der `*` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  

 Dieses Beispiel verwendet den- `*` Operator, um zwei Zahlen zu multiplizieren. Das Ergebnis ist das Produkt der beiden-Operanden.  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Operator * =](multiplication-assignment-operator.md)
- [Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
