---
title: Static (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e08f46076281e766a5bc0b99cd61fee9cd41ece5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
