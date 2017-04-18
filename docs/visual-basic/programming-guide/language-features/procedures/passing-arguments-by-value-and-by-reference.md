---
title: "Übergeben von Argumenten als Wert und als Verweis (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- ByRef keyword, passing arguments by reference
- Visual Basic code, procedures
- passing arguments, by value or by reference
- ByVal keyword, passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing, by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 56d1ceba14020ca7f3dc750c2318efd3e9586af0
ms.lasthandoff: 03/13/2017

---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a>Übergeben von Argumenten als Wert und als Verweis (Visual Basic)
In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], können Sie ein Argument an eine Prozedur übergeben *Wert* oder *als Verweis*. Dies wird als bezeichnet die *übergeben Mechanismus*, und es wird bestimmt, ob die Prozedur das Programmelement, das dem Argument im Aufrufcode zugrunde liegt ändern kann. Die Prozedurdeklaration wird der Übergabemechanismus für jeden Parameter durch Angabe der [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) Schlüsselwort.  
  
## <a name="distinctions"></a>Unterschiede  
 Wenn ein Argument an eine Prozedur übergeben, achten Sie auf mehrere verschiedene Unterschiede, die miteinander interagieren:  
  
-   Gibt an, ob das zugrunde liegende Programmierelement änderbar oder nicht veränderbar ist  
  
-   Gibt an, ob das Argument selbst änderbar oder nicht veränderbar ist  
  
-   Gibt an, ob wird das Argument als Wert oder als Verweis übergeben wird  
  
-   Gibt an, ob der Datentyp des Arguments ein Werttyp oder ein Verweistyp ist  
  
 Weitere Informationen finden Sie unter [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md) und [Unterschiede zwischen übergeben von Argumenten nach Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="choice-of-passing-mechanism"></a>Auswahl der Standardmechanismus zum übergeben  
 Sie sollten die Übergabemechanismus für jedes Argument sorgfältig auswählen.  
  
-   **Schutz**. Bei der Wahl zwischen zwei übergeben Mechanismen, ist das wichtigste Kriterium die Offenlegung von geändert. Der Vorteil der Argumentübergabe `ByRef` besteht darin, dass die Prozedur einen Wert an den aufrufenden Code durch dieses Argument zurückgeben kann. Der Vorteil der Argumentübergabe `ByVal` besteht darin, dass es dadurch verhindert, dass eine Variable, die von der Prozedur geändert wird.  
  
-   **Leistung**. Obwohl die Methode übergeben, die Leistung Ihres Codes auswirken kann, ist in der Regel unbedeutend. Eine Ausnahme ist ein übergebener Werttyp `ByVal`. In diesem Fall [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] kopiert den gesamten Inhalt des Arguments. Aus diesem Grund für einen hohen Wert wie z. B. eine Struktur, es kann effizienter sein übergeben `ByRef`.  
  
     Bei Verweistypen wird nur der Zeiger auf die Daten kopiert (vier Bytes auf 32-Bit-Plattformen, 8 Bytes auf 64-Bit-Plattformen). Deshalb können Sie Argumente des Typs übergeben `String` oder `Object` Wert ohne Leistungseinbußen.  
  
## <a name="determination-of-the-passing-mechanism"></a>Bestimmung des Mechanismus übergeben  
 Die Prozedurdeklaration gibt den Übergabemechanismus für jeden Parameter. Der aufrufende Code kann nicht überschrieben werden ein `ByVal` Mechanismus.  
  
 Wenn ein Parameter mit deklariert ist `ByRef`, der aufrufende Code kann den Mechanismus zum erzwingen `ByVal` durch den Namen des Arguments in Klammern im Aufruf einschließen. Weitere Informationen finden Sie unter [Gewusst wie: erzwingen, dass ein Argument als Wert übergeben werden](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
 Die Standardeinstellung für [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Argumente als Wert übergeben wird.  
  
## <a name="when-to-pass-an-argument-by-value"></a>Wenn ein Argument als Wert übergeben.  
  
-   Wenn der aufrufende Code-Element, das dem Argument zugrunde liegt ein nicht änderbares Element ist, deklarieren Sie den entsprechenden Parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Kein Code kann den Wert eines nicht veränderbaren Elements ändern.  
  
-   Wenn das zugrunde liegende Element geändert werden kann, aber nicht, dass die Prozedur den Wert ändern können möchten, deklarieren Sie den Parameter `ByVal`. Nur der aufrufende Code kann den Wert eines änderbaren Elements übergebener Wert ändern.  
  
## <a name="when-to-pass-an-argument-by-reference"></a>Wenn ein Argument als Verweis übergeben  
  
-   Die Prozedur unbedingt das zugrunde liegende Element im Aufrufcode ändern muss, deklarieren Sie den entsprechenden Parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).  
  
-   Wenn die richtige Ausführung des Codes für die Prozedur das zugrunde liegende Element im Aufrufcode ändern abhängig ist, deklarieren Sie den Parameter `ByRef`. Wenn er als Wert übergeben, oder wenn der aufrufende Code überschreibt die `ByRef` Mechanismus übergeben, indem das Argument in Klammern ein, den Aufruf der Prozedur möglicherweise zu unerwarteten Ergebnissen führen.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im folgende Beispiel wird veranschaulicht, wann zur Übergabe von Argumenten als Wert und wann sie als Verweis übergeben. Prozedur `Calculate` verfügt sowohl über eine `ByVal` und ein `ByRef` Parameter. Erhält einen Zinssatz `rate`, und einer Geldsumme, `debt`, berechnen Sie einen neuen Wert für die Aufgabe der Prozedur ist `debt` , das Ergebnis der Anwendung von der Zinssatz auf den ursprünglichen Wert des `debt`. Da `debt` ist ein `ByRef` -Parameter, die neue Summe wirkt sich der Wert des Arguments in den aufrufenden Code, der entspricht `debt`. Parameter `rate` ist ein `ByVal` Parameter da `Calculate` sollten den Wert nicht ändern.  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbcnProcedures&#74;](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)   
 [Gewusst wie: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)   
 [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Gewusst wie: erzwingen, dass ein Argument als Wert übergeben werden](./how-to-force-an-argument-to-be-passed-by-value.md)   
 [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)   
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
