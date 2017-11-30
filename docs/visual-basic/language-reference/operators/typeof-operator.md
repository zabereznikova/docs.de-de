---
title: TypeOf-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 51bd2af7af28aa229fa62770c5b92d31e461333b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="typeof-operator-visual-basic"></a>TypeOf-Operator (Visual Basic)
Vergleicht eine Objektverweisvariable mit einem Datentyp.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = TypeOf objectexpression Is typename  
```  
  
```  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Wird zurückgegeben. Ein `Boolean`-Wert.  
  
 `objectexpression`  
 Erforderlich. Jeder Ausdruck, der als ein Verweistyp ausgewertet wird.  
  
 `typename`  
 Erforderlich. Ein beliebiger Datentypname.  
  
## <a name="remarks"></a>Hinweise  
 Der `TypeOf`-Operator bestimmt, ob der Laufzeittyp von `objectexpression` mit `typename` kompatibel ist. Die Kompatibilität hängt von der Typkategorie von `typename` ab. Die folgende Tabelle zeigt, wie die Kompatibilität bestimmt wird.  
  
|Typkategorie von `typename`|Kompatibilitätskriterium|  
|---------------------------------|-----------------------------|  
|Klasse|`objectexpression` ist vom Typ `typename` oder erbt von `typename`|  
|Struktur|`objectexpression` ist vom Typ `typename`|  
|Schnittstelle|`objectexpression` implementiert `typename` oder erbt von einer Klasse, die `typename` implementiert|  
  
 Wenn der Laufzeittyp von `objectexpression` das Kompatibilitätskriterium erfüllt, ist `result` `True`. Andernfalls ist `result` `False`.  Wenn `objectexpression` null ist, dann gibt `TypeOf`...`Is` `False` zurück, und ...`IsNot` gibt `True` zurück.  
  
 `TypeOf` wird immer mit dem Schlüsselwort `Is` verwendet, um einen `TypeOf`...`Is`-Ausdruck zu erstellen, oder mit dem Schlüsselwort `IsNot`, um einen `TypeOf`...`IsNot`-Ausdruck zu erstellen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden `TypeOf`...`Is`-Ausdrücke zum Testen der Typkompatibilität von zwei Objektverweisvariablen mit verschiedenen Datentypen verwendet.  
  
 [!code-vb[VbVbalrOperators#39](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/typeof-operator_1.vb)]  
  
 Die Variable `refInteger` verfügt über einen Laufzeittyp von `Integer`. Sie ist mit `Integer`, jedoch nicht mit `Double` kompatibel. Die Variable `refForm` verfügt über einen Laufzeittyp von <xref:System.Windows.Forms.Form>. Sie ist mit <xref:System.Windows.Forms.Form> kompatibel, da es sich hierbei um ihren Typ handelt, sowie mit <xref:System.Windows.Forms.Control>, da <xref:System.Windows.Forms.Form> von <xref:System.Windows.Forms.Control> erbt, und mit <xref:System.ComponentModel.IComponent>, da <xref:System.Windows.Forms.Form> von <xref:System.ComponentModel.Component> erbt, welche wiederum <xref:System.ComponentModel.IComponent> implementiert. `refForm` ist jedoch mit <xref:System.Windows.Forms.Label> nicht kompatibel.  
  
## <a name="see-also"></a>Siehe auch  
 [Is-Operator](../../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Vergleichsoperatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
