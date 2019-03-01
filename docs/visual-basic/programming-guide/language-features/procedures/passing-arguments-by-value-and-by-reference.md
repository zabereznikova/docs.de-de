---
title: Übergeben von Argumenten als Wert und als Verweis (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
ms.openlocfilehash: c2c778afea90a90b2b5f83300c2d174db39f3c15
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978474"
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a>Übergeben von Argumenten als Wert und als Verweis (Visual Basic)
Sie können ein Argument an eine Prozedur übergeben, in Visual Basic *nach Wert* oder *Verweisübergabe*. Dies bezeichnet man als den *Übergabemechanismus*, und es wird bestimmt, ob die Prozedur das Programmierelement zugrunde liegenden Arguments im aufrufenden Code ändern kann. Der Prozedurdeklaration des Übergabemechanismus für die einzelnen Parameter durch Angabe der [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) Schlüsselwort.  
  
## <a name="distinctions"></a>Unterschiede  
 Wenn ein Argument an eine Prozedur übergeben werden, achten Sie darauf, dass Sie von mehreren verschiedenen Unterschiede, die miteinander interagieren:  
  
-   Gibt an, ob das zugrunde liegende Programmierelement geändert werden kann oder nicht veränderbar ist  
  
-   Gibt an, ob das Argument selbst geändert werden kann oder nicht veränderbar ist  
  
-   Gibt an, ob das Argument als Wert oder als Verweis übergebenen  
  
-   Gibt an, ob der Datentyp des Arguments ein Werttyp oder ein Referenztyp ist  
  
 Weitere Informationen finden Sie unter [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md) und [Unterschiede zwischen Argumentübergabe nach Wert "und" By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="choice-of-passing-mechanism"></a>Auswahl des Übergabemechanismus  
 Sie sollten den Übergabemechanismus für jedes Argument sorgfältig auswählen.  
  
-   **Schutz**. Bei der Auswahl zwischen den zwei übergeben Mechanismen, ist das wichtigste Kriterium für die Offenlegung von Aufrufen der Variablen ändern. Der Vorteil der Übergabe eines Arguments `ByRef` besteht darin, dass die Prozedur einen Wert an den aufrufenden Code durch dieses Argument zurückgeben kann. Der Vorteil der Übergabe eines Arguments `ByVal` besteht darin, dass es sich um eine Variable schützt, von der Prozedur geändert werden.  
  
-   **Leistung**. Obwohl es sich bei der Übergabemechanismus die Leistung Ihres Codes auswirken kann, ist in der Regel unbedeutend. Einzige Ausnahme hierbei ist ein Werttyp übergeben `ByVal`. In diesem Fall kopiert Visual Basic den gesamten Inhalt des Arguments. Aus diesem Grund für einen großen Werttyp z. B. eine Struktur, es kann effizienter sein übergeben `ByRef`.  
  
     Für Verweistypen ist nur der Zeiger auf die Daten kopiert (vier Bytes auf 32-Bit-Plattformen, 8 Bytes auf 64-Bit-Plattformen). Aus diesem Grund können Sie Argumente des Typs übergeben `String` oder `Object` als Wert ohne Leistungseinbußen.  
  
## <a name="determination-of-the-passing-mechanism"></a>Bestimmung des dem Übergabemechanismus  
 Deklaration der Prozedur gibt, an dem Übergabemechanismus für jeden Parameter. Der aufrufende Code kann nicht überschrieben. eine `ByVal` Mechanismus.  
  
 Wenn ein Parameter mit deklariert wird `ByRef`, der aufrufende Code kann den Mechanismus zum erzwingen `ByVal` indem der Name des Arguments in Klammern angegeben im Aufruf. Weitere Informationen finden Sie unter [Vorgehensweise: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
 Der Standardwert in Visual Basic ist, Argumente als Wert übergeben.  
  
## <a name="when-to-pass-an-argument-by-value"></a>Wenn ein Argument als Wert übergeben.  
  
-   Wenn der aufrufende Code-Element, das dem Argument zugrunde liegt ein nicht veränderbares Element ist, deklarieren Sie den entsprechenden Parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Kein Code kann es sich um den Wert eines Elements als nicht änderbar ändern.  
  
-   Wenn das zugrunde liegende Element geändert werden kann, aber nicht, dass das Verfahren, um den Wert ändern zu können möchten, deklarieren Sie den Parameter `ByVal`. Nur der aufrufende Code kann es sich um den Wert eines änderbaren Elements als Wert übergeben, ändern.  
  
## <a name="when-to-pass-an-argument-by-reference"></a>Wenn ein Argument als Verweis zu übergeben.  
  
-   Verfügt die Prozedur eine Notwendigkeit so ändern Sie das zugrunde liegende Element im aufrufenden Code, deklarieren Sie den entsprechenden Parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).  
  
-   Wenn die richtige Ausführung des Codes für die Prozedur ändern das zugrunde liegende Element im aufrufenden Code abhängig ist, deklarieren Sie den Parameter `ByRef`. Wenn Sie ihn als Wert übergeben oder wenn der aufrufende Code überschreibt die `ByRef` Übergabemechanismus, indem das Argument in Klammern ein, den Aufruf der Prozedur kann zu unerwarteten Ergebnissen führen.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel veranschaulicht, Argumente als Wert übergeben und von ihnen als Verweis zu übergeben. Prozedur `Calculate` weist sowohl ein `ByVal` und `ByRef` Parameter. Erhält einen Zinssatz `rate`, und einer Geldsumme, `debt`, die Aufgabe der Prozedur ist, berechnen Sie einen neuen Wert für `debt` , das Ergebnis des Anwendens von den Zinssatz auf den ursprünglichen Wert von `debt`. Da `debt` ist eine `ByRef` -Parameter dem neuen Gesamtbetrag wirkt sich der Wert des Arguments im aufrufenden Code, der entspricht `debt`. Parameter `rate` ist eine `ByVal` Parameter da `Calculate` ändern Sie seinen Wert nicht sollten.  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbcnProcedures#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class2.vb#74)]  
  
## <a name="see-also"></a>Siehe auch
- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Vorgehensweise: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Vorgehensweise: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)
- [Vorgehensweise: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Vorgehensweise: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
