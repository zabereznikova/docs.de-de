---
title: Static (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 1205d620fb5b6ec6af14cdeb7c6d78439f9e6b97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627628"
---
# <a name="static-visual-basic"></a>Static (Visual Basic)
Gibt an, dass eine oder mehrere deklarierte Variablen sind weiterhin vorhanden, und behalten ihre aktuellen Werte nach dem Beenden der Prozedur, in der sie deklariert werden.  
  
## <a name="remarks"></a>Hinweise  
 Normalerweise wird eine lokale Variable in einer Prozedur vorhanden ist, sobald die Prozedur beendet wird. Eine statische Variable bleibt erhalten und den aktuellen Wert beibehält. Das nächste Mal, das der Code der Prozedur wird, die Variable wird nicht erneut initialisiert, und sie behält den aktuellen Wert, den Sie zugewiesen. Eine statische Variable bleibt für die Lebensdauer der Klasse oder des Moduls vorhanden sein, die sie in definiert ist.  
  
## <a name="rules"></a>Regeln  
  
-   **Deklarationskontext.** Sie können `Static` nur für lokale Variablen. Dies bedeutet, dass der Deklarationskontext für eine `Static` Variable muss eine Prozedur oder einen Block in einer Prozedur, und ist nicht möglich Quelldatei, Namespace, Klasse, Struktur oder Moduls.  
  
     Sie können keine `Static` innerhalb einer Strukturprozedur.  
  
-   Die Datentypen der `Static` lokale Variablen können nicht abgeleitet werden. Weitere Informationen finden Sie unter [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
-   **Kombinierte Modifizierer.** Sie können keine angeben `Static` zusammen mit `ReadOnly`, `Shadows`, oder `Shared` in der gleichen Deklaration.  
  
## <a name="behavior"></a>Verhalten  
 Wenn Sie deklarieren eine statische Variable in einem `Shared` Verfahren nur eine Kopie der statischen Variable steht für die gesamte Anwendung. Rufen Sie eine `Shared` name Prozedur mithilfe der Klasse, die nicht auf eine Variable, die auf eine Instanz der Klasse verweist.  
  
 Wenn Sie eine statische Variable in einer Prozedur, die nicht deklarieren `Shared`, nur eine Kopie der Variablen für jede Instanz der Klasse zur Verfügung steht. Sie können eine nicht freigegebene Prozedur aufrufen, mithilfe einer Variablen, die auf eine bestimmte Instanz der Klasse verweist.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](../../../visual-basic/language-reference/codesnippet/VisualBasic/static_1.vb)]  
  
 Die `Static` Variable `totalSales` wird nur ein Mal mit 0 initialisiert. Jedes Mal, den Sie eingeben `updateSales`, `totalSales` noch immer den letzten Wert an, die Sie dafür berechnet.  
  
 Die `Static` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>Siehe auch
- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Lebensdauer in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Variablendeklaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
