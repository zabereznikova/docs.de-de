---
title: Übergeben von Argumenten als Wert und als Verweis (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f10e0e582e060c1305a9c0fe922620cb4da2c215
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a>Übergeben von Argumenten als Wert und als Verweis (Visual Basic)
In Visual Basic können Sie ein Argument an eine Prozedur übergeben *nach Wert* oder *Verweisübergabe*. Dies bezeichnet man die *Übergabemechanismus*, und sie bestimmt, ob die Prozedur das Programmierelement zugrunde liegt das Argument im aufrufenden Code ändern kann. Der Prozedurdeklaration des Übergabemechanismus für jeden Parameter durch Angabe der [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) Schlüsselwort.  
  
## <a name="distinctions"></a>Unterschiede  
 Wenn ein Argument an eine Prozedur übergeben, achten Sie auf mehrere verschiedene Unterschiede, die miteinander interagieren:  
  
-   Gibt an, ob das zugrunde liegende Programmierelement geändert werden kann oder nicht veränderbar ist  
  
-   Gibt an, ob das Argument selbst geändert werden kann oder nicht veränderbar ist  
  
-   Gibt an, ob das Argument als Wert oder als Verweis übergeben wird wird  
  
-   Gibt an, ob der Datentyp des Arguments ein Werttyp oder ein Verweistyp ist  
  
 Weitere Informationen finden Sie unter [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md) und [Unterschiede zwischen übergibt ein Argument nach Wert und nach Referenz](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="choice-of-passing-mechanism"></a>Wahl des Übergabemechanismus  
 Sie sollten den Übergabemechanismus für jedes Argument sorgfältig auswählen.  
  
-   **Schutz**. Bei der Wahl zwischen den Mechanismen zwei übergeben, ist das wichtigste Kriterium das Offenlegen von Aufrufen der Variablen ändern. Der Vorteil der Übergabe eines Arguments `ByRef` darin, dass die Prozedur einen Wert an den aufrufenden Code über dieses Argument zurückgeben kann. Der Vorteil der Übergabe eines Arguments `ByVal` ist, dass es dadurch verhindert, dass eine Variable, die von der Prozedur geändert wird.  
  
-   **Leistung**. Obwohl es sich bei der Übergabemechanismus auf die Leistung des Codes auswirken kann, ist der Unterschied in der Regel nicht signifikante. Einzige Ausnahme hierbei ist ein Werttyp übergeben `ByVal`. In diesem Fall kopiert Visual Basic den gesamten Inhalt des Arguments. Aus diesem Grund für einen großen Werttyp z. B. eine Struktur, es kann effizienter sein zur Übergabe `ByRef`.  
  
     Für Verweistypen ist nur die Zeiger auf die Daten kopiert (vier Bytes auf 32-Bit-Plattformen, 8 Bytes auf 64-Bit-Plattformen). Aus diesem Grund können Sie Argumente des Typs übergeben `String` oder `Object` als Wert ohne Leistungseinbußen.  
  
## <a name="determination-of-the-passing-mechanism"></a>Bestimmung der dem Übergabemechanismus  
 Der Deklaration der Prozedur gibt dem Übergabemechanismus für jeden Parameter an. Der aufrufende Code kann nicht überschrieben werden eine `ByVal` Mechanismus.  
  
 Wenn ein Parameter mit deklariert wird `ByRef`, der aufrufende Code kann erzwingen, dass den Mechanismus zum `ByVal` durch Einschließen von Name des Arguments in Klammern im Aufruf. Weitere Informationen finden Sie unter [wie: erzwingen, dass ein Argument als Wert übergeben werden](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
 Der Standardwert in Visual Basic ist Argumenten als Wert übergeben.  
  
## <a name="when-to-pass-an-argument-by-value"></a>Wenn ein Argument als Wert übergeben.  
  
-   Der aufrufende Code-Element, das dem Argument zugrunde liegt ein nicht veränderbares Element, deklarieren Sie die entsprechenden Parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Kein Code kann den Wert eines Elements nicht veränderbaren ändern.  
  
-   Wenn das zugrunde liegende Element geändert werden kann wird, aber nicht, dass die Prozedur den Wert ändern können möchten, deklarieren Sie den Parameter `ByVal`. Nur der aufrufende Code kann den Wert eines änderbaren Elements nach Wert übergeben ändern.  
  
## <a name="when-to-pass-an-argument-by-reference"></a>Wenn ein Argument als Verweis übergeben werden.  
  
-   Die Prozedur eine Notwendigkeit so ändern Sie das zugrunde liegende Element im aufrufenden Code aufweist, deklarieren Sie den entsprechenden Parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).  
  
-   Wenn die Prozedur, die die zugrunde liegende Element im aufrufenden Code ändert die korrekte Ausführung des Codes abhängig ist, deklarieren Sie den Parameter `ByRef`. Wenn Sie ihn als Wert übergeben, oder wenn der aufrufende Code überschreibt die `ByRef` Übergabemechanismus, indem das Argument in Klammern einschließen, der Prozeduraufruf kann zu unerwarteten Ergebnissen führen.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel veranschaulicht die Argumente als Wert übergeben und als Verweis zu übergeben. Prozedur `Calculate` verfügt sowohl über eine `ByVal` und ein `ByRef` Parameter. Erhält einen Zinssatz `rate`, und einer Geldsumme, `debt`, die Aufgabe der Prozedur ist, um einen neuen Wert zu berechnen `debt` d. h. das Ergebnis des Anwendens von den Zinssatz auf den ursprünglichen Wert des `debt`. Da `debt` ist ein `ByRef` -Parameter den Wert des Arguments in den aufrufenden Code, der entspricht dem neuen Gesamtwert wiedergegeben `debt`. Parameter `rate` ist ein `ByVal` Parameter da `Calculate` sollten den Wert nicht ändern.  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbcnProcedures#74](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)  
 [Gewusst wie: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)  
 [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)  
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
