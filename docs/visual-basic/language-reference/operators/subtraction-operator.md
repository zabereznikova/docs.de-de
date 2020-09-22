---
title: '- Operator'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: b5129c2dbb361940fa6da2cb424ee23736ba72c5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875333"
---
# <a name="--operator-visual-basic"></a>--Operator (Visual Basic)

Gibt die Differenz zwischen zwei numerischen Ausdrücken oder dem negativen Wert eines numerischen Ausdrucks zurück.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
expression1 – expression2
```
  
oder

```vb  
–expression1  
```  
  
## <a name="parts"></a>Bestandteile  

 `expression1`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich, es sei denn, der `–` Operator berechnet einen negativen Wert. Ein beliebiger numerischer Ausdruck.  
  
## <a name="result"></a>Ergebnis  

 Das Ergebnis ist der Unterschied zwischen `expression1` und `expression2` oder dem negiert Wert von `expression1` .  
  
 Der Ergebnis Datentyp ist ein numerischer Typ, der für die Datentypen von und geeignet ist `expression1` `expression2` . Weitere Informationen finden Sie in den Tabellen "ganzzahlige Arithmetik" unter [Datentypen von Operator Ergebnissen](data-types-of-operator-results.md)  
  
## <a name="supported-types"></a>Unterstützte Typen  

 allen numerischen Typen Dies schließt die unsignierten-und Gleit Komma Typen und ein `Decimal` .  
  
## <a name="remarks"></a>Bemerkungen  

 In der ersten Verwendung, die in der zuvor gezeigten Syntax gezeigt wurde, `–` ist der Operator der *binäre* arithmetische Subtraktions Operator für den Unterschied zwischen zwei numerischen Ausdrücken.  
  
 In der zweiten Syntax, die in der zuvor gezeigten Syntax angezeigt wird, `–` ist der Operator der *unäre* Negations Operator für den negativen Wert eines Ausdrucks. In diesem Sinne besteht die Negation darin, das Vorzeichen von umzukehren, `expression1` sodass das Ergebnis positiv ist, wenn `expression1` negativ ist.  
  
 Wenn ein Ausdruck zu " [Nothing](../nothing.md)" ausgewertet wird, `–` behandelt der Operator ihn als 0 (null).  
  
> [!NOTE]
> Der `–` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird der- `–` Operator verwendet, um die Differenz zwischen zwei Zahlen zu berechnen und zurückzugeben und dann eine Zahl zu negieren.  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 Nach der Ausführung dieser Anweisungen `binaryResult` enthält 124,45 und `unaryResult` enthält – 334,90.  
  
## <a name="see-also"></a>Weitere Informationen

- [Operator-= (Visual Basic)](subtraction-assignment-operator.md)
- [Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
