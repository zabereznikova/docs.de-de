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
ms.openlocfilehash: 9d1e327c25689bed1405ea9a627da6232abb707b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392947"
---
# <a name="declared-element-characteristics-visual-basic"></a>Merkmale deklarierter Elemente (Visual Basic)
Ein *Merkmal* eines deklarierten Elements ist ein Aspekt dieses Elements, das beeinflusst, wie Code mit ihm interagieren kann. Jedem deklarierten Element sind mindestens eine der folgenden Eigenschaften zugeordnet:  
  
- *Datentyp* – die Werte, die das Element enthalten kann, und wie diese Werte gespeichert werden. Weitere Informationen finden Sie unter [Datentypen](../../../language-reference/data-types/index.md).  
  
- *Lifetime* – der Zeitraum der Ausführungszeit, in der das Element zur Verwendung verfügbar ist. Weitere Informationen finden Sie unter [Lebensdauer in Visual Basic](lifetime.md).  
  
- *Bereich* – der Satz des gesamten Codes, der auf das Element verweisen kann, ohne den Namen zu qualifizieren. Weitere Informationen finden Sie unter Gewusst [wie: Steuern des Gültigkeits Bereichs einer Variablen](how-to-control-the-scope-of-a-variable.md).  
  
- *Zugriffsebene* – die Berechtigung für den Code, um das-Element zu verwenden. Weitere Informationen finden Sie unter Gewusst [wie: Steuern der Verfügbarkeit einer Variablen](how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Merkmale der Elemente  
 In der folgenden Tabelle werden die deklarierten Elemente und die Merkmale, die für die einzelnen Elemente gelten, angezeigt.  
  
|Element|Datentyp|Lebensdauer|Bereich <sup>1</sup>|Zugriffsebene|  
|-------------|---------------|--------------|------------------------|------------------|  
|Variable|Ja|Ja|Ja|Ja|  
|Konstante|Ja|Nein|Ja|Ja|  
|Enumeration|Ja|Nein|Ja|Ja|  
|Struktur|Nein|Nein |Ja|Ja|  
|Eigenschaft|Ja|Ja|Ja|Ja|  
|Methode|Nein |Ja|Ja|Ja|  
|Prozedur ( `Sub` oder `Function` )|Nein |Ja|Ja|Ja|  
|Prozedurparameter|Ja|Ja|Ja|Nein|  
|Funktions Rückgabe|Ja|Ja|Ja|Nein|  
|Operator|Ja|Nein|Ja|Ja|  
|Schnittstelle|Nein|Nein |Ja|Ja|  
|Klasse|Nein|Nein |Ja|Ja|  
|Ereignis|Nein|Nein |Ja|Ja|  
|Delegat|Nein|Nein |Ja|Ja|  
  
 <sup>1</sup> der Bereich wird manchmal als *Sichtbarkeit*bezeichnet.  
  
## <a name="see-also"></a>Weitere Informationen

- [Deklarierte Elemente](index.md)
- [Declared Element Names](declared-element-names.md)
- [References to Declared Elements](references-to-declared-elements.md)
- [Lebensdauer in Visual Basic](lifetime.md)
- [Gültigkeitsbereich in Visual Basic](scope.md)
- [Zugriffsebenen in Visual Basic](access-levels.md)
- [Datentypen](../data-types/index.md)
- [Variablen Deklaration](../variables/variable-declaration.md)
