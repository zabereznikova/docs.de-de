---
title: Merkmale deklarierter Elemente (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 26ee27d3a1d085c6ab45ae850dbdac700aa208a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="declared-element-characteristics-visual-basic"></a>Merkmale deklarierter Elemente (Visual Basic)
Ein *Merkmal* eines deklarierten Elements ist ein Aspekt des jeweiligen Elements, die beeinflussen, wie Code mit ihm interagieren kann. Jedem deklariertes Element verfügt über eine oder mehrere der folgenden Eigenschaften zugeordnet:  
  
-   *Datentyp* – die Werte, die das Element enthalten kann, und wie diese Werte gespeichert. Weitere Informationen finden Sie unter [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
-   *Lebensdauer* – den Zeitraum der Ausführungszeit, die während der das Element für die Verwendung verfügbar ist. Weitere Informationen finden Sie unter [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   *Bereich* – die Menge des gesamten Codes, die auf das Element verweisen kann, ohne dessen Namen zu qualifizieren. Weitere Informationen finden Sie unter [wie: Steuern des Gültigkeitsbereichs einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md).  
  
-   *Zugriffsebene* – die Berechtigung für Code, um, der das Element verwenden. Weitere Informationen finden Sie unter [wie: Steuern der Verfügbarkeit einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Merkmale der Elemente  
 Die folgende Tabelle zeigt deklarierte Elemente und die Eigenschaften, die für jede Anwendung gelten.  
  
|Element|Datentyp|Lebensdauer|Bereich <sup>1</sup>|Zugriffsebene|  
|-------------|---------------|--------------|------------------------|------------------|  
|Variable|Ja|Ja|Ja|Ja|  
|Konstante|Ja|Nein|Ja|Ja|  
|Enumeration|Ja|Nein|Ja|Ja|  
|Struktur|Nein|Nein|Ja|Ja|  
|Eigenschaft|Ja|Ja|Ja|Ja|  
|Methode|Nein|Ja|Ja|Ja|  
|Prozedur (`Sub` oder `Function`)|Nein|Ja|Ja|Ja|  
|Prozedurparameter|Ja|Ja|Ja|Nein|  
|Return-Funktion|Ja|Ja|Ja|Nein|  
|Operator|Ja|Nein|Ja|Ja|  
|Schnittstelle|Nein|Nein|Ja|Ja|  
|Klasse|Nein|Nein|Ja|Ja|  
|Ereignis|Nein|Nein|Ja|Ja|  
|Delegate|Nein|Nein|Ja|Ja|  
  
 <sup>1</sup> Bereich wird manchmal als *Sichtbarkeit*.  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
