---
title: Operator TypeOf
ms.date: 07/20/2015
f1_keywords:
- TypeOf
- vb.TypeOf
helpviewer_keywords:
- types [Visual Basic], compatible
- comparison operators [Visual Basic]
- TypeOf...Is expression
- data types [Visual Basic], compatible
- TypeOf operator [Visual Basic]
- compatible data types [Visual Basic]
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
ms.openlocfilehash: 0cce36073b53442bce63f966f3bd94bd5d70d2a8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406326"
---
# <a name="typeof-operator-visual-basic"></a>TypeOf-Operator (Visual Basic)
Überprüft, ob der Lauf Zeittyp des Ergebnisses eines Ausdrucks typkompatibel mit dem angegebenen Typ ist.
  
## <a name="syntax"></a>Syntax  
  
```vb  
result = TypeOf objectexpression Is typename  
```  
  
```vb  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a>Bestandteile  
 `result`  
 Wird zurückgegeben. Ein `Boolean`-Wert.  
  
 `objectexpression`  
 Erforderlich. Jeder Ausdruck, der als ein Verweistyp ausgewertet wird.  
  
 `typename`  
 Erforderlich. Ein beliebiger Datentypname.  
  
## <a name="remarks"></a>Bemerkungen  
 Der `TypeOf`-Operator bestimmt, ob der Laufzeittyp von `objectexpression` mit `typename` kompatibel ist. Die Kompatibilität hängt von der Typkategorie von `typename` ab. Die folgende Tabelle zeigt, wie die Kompatibilität bestimmt wird.  
  
|Typkategorie von `typename`|Kompatibilitätskriterium|  
|---------------------------------|-----------------------------|  
|Klasse|`objectexpression` ist vom Typ `typename` oder erbt von `typename`|  
|Struktur|`objectexpression` ist vom Typ `typename`|  
|Schnittstelle|`objectexpression` implementiert `typename` oder erbt von einer Klasse, die `typename` implementiert|  
  
 Wenn der Laufzeittyp von `objectexpression` das Kompatibilitätskriterium erfüllt, ist `result``True`. Andernfalls lautet `result``False`.  Wenn `objectexpression` null ist, dann gibt `TypeOf`...`Is``False` zurück, und ...`IsNot` gibt `True` zurück.  
  
 `TypeOf` wird immer mit dem Schlüsselwort `Is` verwendet, um einen `TypeOf`...`Is`-Ausdruck zu erstellen, oder mit dem Schlüsselwort `IsNot`, um einen `TypeOf`...`IsNot`-Ausdruck zu erstellen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden `TypeOf`...`Is`-Ausdrücke zum Testen der Typkompatibilität von zwei Objektverweisvariablen mit verschiedenen Datentypen verwendet.  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 Die Variable `refInteger` verfügt über einen Laufzeittyp von `Integer`. Sie ist mit `Integer`, jedoch nicht mit `Double` kompatibel. Die Variable `refForm` verfügt über einen Laufzeittyp von <xref:System.Windows.Forms.Form>. Sie ist mit <xref:System.Windows.Forms.Form> kompatibel, da es sich hierbei um ihren Typ handelt, sowie mit <xref:System.Windows.Forms.Control>, da <xref:System.Windows.Forms.Form> von <xref:System.Windows.Forms.Control> erbt, und mit <xref:System.ComponentModel.IComponent>, da <xref:System.Windows.Forms.Form> von <xref:System.ComponentModel.Component> erbt, welche wiederum <xref:System.ComponentModel.IComponent> implementiert. `refForm` ist jedoch mit <xref:System.Windows.Forms.Label> nicht kompatibel.  
  
## <a name="see-also"></a>Weitere Informationen

- [Is-Operator](is-operator.md)
- [IsNot-Operator](isnot-operator.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Operatoren und Ausdrücke](../../programming-guide/language-features/operators-and-expressions/index.md)
