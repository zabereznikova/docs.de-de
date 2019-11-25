---
title: Merkmale deklarierter Elemente
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], lifetime
- access levels, declared elements
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- elements [Visual Basic], programming
- scope [Visual Basic], declared elements
- lifetime [Visual Basic], declared elements
- declared elements [Visual Basic], access level
- data types [Visual Basic], declared elements
- declared elements [Visual Basic], visibility
ms.assetid: 1bc40fb8-b67c-4428-90a4-76b630ae2583
ms.openlocfilehash: 4e03cd28fed5e0ae109337739251c11a0ff3424a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331625"
---
# <a name="declared-element-characteristics-visual-basic"></a>Merkmale deklarierter Elemente (Visual Basic)
A *characteristic* of a declared element is an aspect of that element that affects how code can interact with it. Every declared element has one or more of the following characteristics associated with it:  
  
- *Data type* — the values the element can hold, and how it stores those values. Weitere Informationen finden Sie unter [Datentypen](../../../../visual-basic/language-reference/data-types/index.md).  
  
- *Lifetime* — the period of execution time during which the element is available for use. For more information, see [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
- *Scope* — the set of all code that can refer to the element without qualifying its name. For more information, see [How to: Control the Scope of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md).  
  
- *Access level* — the permission for code to make use of the element. For more information, see [How to: Control the Availability of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Characteristics of the Elements  
 The following table shows the declared elements and the characteristics that apply to each one.  
  
|Element|Datentyp|Lebensdauer|Scope <sup>1</sup>|Access Level|  
|-------------|---------------|--------------|------------------------|------------------|  
|Variable|Ja|Ja|Ja|Ja|  
|Konstante|Ja|Nein|Ja|Ja|  
|Enumeration|Ja|Nein|Ja|Ja|  
|Struktur|Nein|Nein|Ja|Ja|  
|property|Ja|Ja|Ja|Ja|  
|Methode|Nein|Ja|Ja|Ja|  
|Procedure (`Sub` or `Function`)|Nein|Ja|Ja|Ja|  
|Prozedurparameter|Ja|Ja|Ja|Nein|  
|Function return|Ja|Ja|Ja|Nein|  
|Operator|Ja|Nein|Ja|Ja|  
|Interface|Nein|Nein|Ja|Ja|  
|Klasse|Nein|Nein|Ja|Ja|  
|event|Nein|Nein|Ja|Ja|  
|delegate|Nein|Nein|Ja|Ja|  
  
 <sup>1</sup> Scope is sometimes referred to as *visibility*.  
  
## <a name="see-also"></a>Siehe auch

- [Deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
