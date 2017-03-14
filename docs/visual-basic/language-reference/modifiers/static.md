---
title: "Static (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Static"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "static modifier"
  - "Static keyword"
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Static (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Legt fest, dass eine oder mehrere deklarierte lokale Variablen nach Beendigung der Prozedur, in der sie deklariert wurden, erhalten bleiben und die letzten Werte beibehalten.  
  
## Hinweise  
 Normalerweise wird eine lokale Variable einer Prozedur gelöscht, sobald die Prozedur beendet wird.  Eine statische Variable bleibt erhalten und behält ihren letzten Wert bei.  Beim nächsten Aufruf der Prozedur wird die Variable nicht neu initialisiert, sondern hat immer noch den Wert, der ihr zuletzt zugewiesen wurde.  Eine statische Variable bleibt so lange bestehen, wie die Klasse oder das Modul, in der bzw. dem sie definiert wurde.  
  
## Regeln  
  
-   **Deklarationskontext.** Sie können `Static` nur für lokale Variablen verwenden.  Das bedeutet, dass der Deklarationskontext einer als `Static` deklarierten Variable eine Prozedur oder ein Block innerhalb einer Prozedur sein muss, nicht aber eine Quelldatei, ein Namespace, eine Klasse, eine Struktur oder ein Modul.  
  
     Sie können `Static` nicht in einer Strukturprozedur verwenden.  
  
-   Die Datentypen von lokalen `Static`\-Variablen können nicht abgeleitet werden.  Weitere Informationen finden Sie unter [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
-   **Kombinierte Modifizierer.** `Static` kann nicht zusammen mit `ReadOnly`, `Shadows` oder `Shared` in derselben Deklaration verwendet werden.  
  
## Verhalten  
 Wenn Sie eine statische Variable in einer `Shared` Prozedur deklarieren, nur eine Kopie der statischen Variablen für die gesamte Anwendung verfügbar ist.  Zum Aufrufen einer `Shared` Prozedur an, indem Sie den Klassennamen keine Variable verwenden, die mit einer Instanz der Klasse verweist.  
  
 Wenn Sie eine statische Variable in einer Prozedur deklarieren, die nicht `Shared` nur eine Kopie der Variable für jede Instanz der Klasse verfügbar ist.  Sie rufen eine nicht freigegebene Schritte an, indem Sie eine Variable verwenden, die einer bestimmten Instanz der Klasse verweist.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](../../../visual-basic/language-reference/codesnippet/VisualBasic/static_1.vb)]  
  
 Die `Static`\-Variable `totalSales` wird nur einmal mit dem Wert 0 \(null\) initialisiert.  Bei jeder Ausführung von `updateSales` enthält `totalSales` den zuletzt berechneten Wert.  
  
 Der `Static`\-Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## Siehe auch  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Lifetime in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Variablendeklaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)