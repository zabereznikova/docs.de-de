---
title: Static (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 2cbd99a026a5ebf0e215ee5732d62ccf639d3836
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602053"
---
# <a name="static-visual-basic"></a>Static (Visual Basic)
Gibt an, dass eine oder mehrere deklarierte lokale Variablen weiterhin vorhanden sein und behalten die neuesten Werte nach dem Beenden der Prozedur, in der sie deklariert werden.  
  
## <a name="remarks"></a>Hinweise  
 Normalerweise wird eine lokale Variable in einer Prozedur vorhanden ist, sobald die Prozedur beendet wird. Eine statische Variable bleibt erhalten und behält den letzten Wert. Das nächste Mal, das Ihr Code die Prozedur aufruft. die Variable wird nicht erneut initialisiert, und sie behält den neuesten-Wert, den Sie zugewiesen. Eine statische Variable bleibt für die Lebensdauer der Klasse oder des Moduls vorhanden sein, die in der Sie definiert ist.  
  
## <a name="rules"></a>Regeln  
  
-   **Deklarationskontext.** Sie können `Static` nur auf lokale Variablen. Dies bedeutet, dass der Deklarationskontext für eine `Static` Variable eine Prozedur oder einen Block in einer Prozedur sein muss, und keine Quelldatei, Namespace, Klasse, Struktur oder Modul.  
  
     Sie können keine `Static` innerhalb einer Strukturprozedur.  
  
-   Die Datentypen der `Static` lokale Variablen können nicht abgeleitet werden. Weitere Informationen finden Sie unter [lokalen Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
-   **Kombinierte Modifizierer.** Sie können keine angeben `Static` zusammen mit `ReadOnly`, `Shadows`, oder `Shared` in der gleichen Deklaration.  
  
## <a name="behavior"></a>Verhalten  
 Wenn Sie eine statische Variable in Deklarieren einer `Shared` Prozedur, die nur eine Kopie der statischen Variablen ist für die gesamte Anwendung verfügbar. Rufen Sie eine `Shared` Prozedur mit der Klasse benennen, nicht auf eine Variable, die auf eine Instanz der Klasse verweist.  
  
 Wenn Sie eine statische Variable in einer Prozedur, die nicht deklarieren `Shared`, nur eine Kopie der Variablen für jede Instanz der Klasse zur Verfügung steht. Rufen Sie eine nicht freigegebene Prozedur mithilfe einer Variablen, die auf eine bestimmte Instanz der Klasse verweist.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](../../../visual-basic/language-reference/codesnippet/VisualBasic/static_1.vb)]  
  
 Die `Static` Variable `totalSales` wird nur einmal mit 0 initialisiert. Jedes Mal, den Sie eingeben `updateSales`, `totalSales` immer noch den letzten Wert an, die Sie dafür berechnet.  
  
 Die `Static` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [Lebensdauer in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Variablendeklaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
