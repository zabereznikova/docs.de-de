---
title: "TypeOf Operator (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TypeOf"
  - "vb.TypeOf"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "types [Visual Basic], compatible"
  - "comparison operators"
  - "TypeOf...Is expression"
  - "data types [Visual Basic], compatible"
  - "TypeOf operator [Visual Basic]"
  - "compatible data types"
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# TypeOf Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Vergleicht eine Objektverweisvariable mit einem Datentyp.  
  
## Syntax  
  
```  
  
result = TypeOf objectexpression Is typename  
```  
  
```  
  
result = TypeOf objectexpression IsNot typename  
```  
  
## Teile  
 `result`  
 Wird zurückgegeben.  Ein `Boolean`\-Wert.  
  
 `objectexpression`  
 Erforderlich.  Jeder Ausdruck, der als ein Verweistyp ausgewertet wird.  
  
 `typename`  
 Erforderlich.  Ein beliebiger Datentypname.  
  
## Hinweise  
 Der `TypeOf`\-Operator bestimmt, ob der Laufzeittyp von `objectexpression` mit `typename` kompatibel ist.  Die Kompatibilität hängt von der Typkategorie von `typename` ab.  Die folgende Tabelle zeigt, wie die Kompatibilität bestimmt wird.  
  
|Typkategorie von `typename`|Kompatibilitätskriterium|  
|---------------------------------|------------------------------|  
|Klasse|`objectexpression` ist vom Typ `typename` oder erbt von `typename`|  
|Struktur|`objectexpression` ist vom Typ `typename`|  
|Schnittstelle|`objectexpression` implementiert `typename` oder erbt von einer Klasse, die `typename` implementiert|  
  
 Wenn der Laufzeittyp von `objectexpression` das Kompatibilitätskriterium erfüllt, ist `result` `True`.  Andernfalls ist `result` `False`.  Wenn `objectexpression` null ist, dann gibt `TypeOf`...`Is` `False` zurück, und ...`IsNot` gibt `True` zurück.  
  
 `TypeOf` wird immer mit dem Schlüsselwort `Is` verwendet, um einen `TypeOf`...`Is`\-Ausdruck zu erstellen, oder mit dem Schlüsselwort `IsNot`, um einen `TypeOf`...`IsNot`\-Ausdruck zu erstellen.  
  
## Beispiel  
 Im folgenden Beispiel werden `TypeOf`...`Is`\-Ausdrücke zum Testen der Typkompatibilität von zwei Objektverweisvariablen mit verschiedenen Datentypen verwendet.  
  
 [!code-vb[VbVbalrOperators#39](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/typeof-operator_1.vb)]  
  
 Die Variable `refInteger` verfügt über einen Laufzeittyp von `Integer`.  Sie ist mit `Integer`, jedoch nicht mit `Double` kompatibel.  Die Variable `refForm` verfügt über einen Laufzeittyp von <xref:System.Windows.Forms.Form>.  Sie ist mit <xref:System.Windows.Forms.Form> kompatibel, da es sich hierbei um ihren Typ handelt, sowie mit <xref:System.Windows.Forms.Control>, da <xref:System.Windows.Forms.Form> von <xref:System.Windows.Forms.Control> erbt, und mit <xref:System.ComponentModel.IComponent>, da <xref:System.Windows.Forms.Form> von <xref:System.ComponentModel.Component> erbt, welche wiederum <xref:System.ComponentModel.IComponent> implementiert.  `refForm` ist jedoch mit <xref:System.Windows.Forms.Label> nicht kompatibel.  
  
## Siehe auch  
 [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)