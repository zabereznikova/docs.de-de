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
Ein *Merkmal* eines deklarierten Elements ist ein Aspekt dieses Elements, das beeinflusst, wie Code mit ihm interagieren kann. Jedem deklarierten Element sind mindestens eine der folgenden Eigenschaften zugeordnet:  
  
- *Datentyp* – die Werte, die das Element enthalten kann, und wie diese Werte gespeichert werden. Weitere Informationen finden Sie unter [Datentypen](../../../../visual-basic/language-reference/data-types/index.md).  
  
- *Lifetime* – der Zeitraum der Ausführungszeit, in der das Element zur Verwendung verfügbar ist. Weitere Informationen finden Sie unter [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
- *Bereich* – der Satz des gesamten Codes, der auf das Element verweisen kann, ohne den Namen zu qualifizieren. Weitere Informationen finden Sie unter Gewusst [wie: Steuern des Gültigkeits Bereichs einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md).  
  
- *Zugriffsebene* – die Berechtigung für den Code, um das-Element zu verwenden. Weitere Informationen finden Sie unter Gewusst [wie: Steuern der Verfügbarkeit einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Merkmale der Elemente  
 In der folgenden Tabelle werden die deklarierten Elemente und die Merkmale, die für die einzelnen Elemente gelten, angezeigt.  
  
|Element|Datentyp|Lebensdauer|Bereich <sup>1</sup>|Zugriffsebene|  
|-------------|---------------|--------------|------------------------|------------------|  
|Variable|Ja|Ja|Ja|Ja|  
|Konstante|Ja|Nein|Ja|Ja|  
|Enumeration|Ja|Nein|Ja|Ja|  
|Struktur|Nein|Nein|Ja|Ja|  
|Die Eigenschaften-|Ja|Ja|Ja|Ja|  
|Methode|Nein|Ja|Ja|Ja|  
|Prozedur (`Sub` oder `Function`)|Nein|Ja|Ja|Ja|  
|Prozedurparameter|Ja|Ja|Ja|Nein|  
|Funktions Rückgabe|Ja|Ja|Ja|Nein|  
|Operator|Ja|Nein|Ja|Ja|  
|Schnittstelle|Nein|Nein|Ja|Ja|  
|Klasse|Nein|Nein|Ja|Ja|  
|Ereignis|Nein|Nein|Ja|Ja|  
|Delegat|Nein|Nein|Ja|Ja|  
  
 <sup>1</sup> der Bereich wird manchmal als *Sichtbarkeit*bezeichnet.  
  
## <a name="see-also"></a>Siehe auch

- [Deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Bereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
