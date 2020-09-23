---
title: Übergeben von Argumenten als Wert und als Verweis
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
ms.openlocfilehash: b7430b209f53a0a924ec587a0097178baf0075e3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059217"
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a>Übergeben von Argumenten als Wert und als Verweis (Visual Basic)

In Visual Basic können Sie ein Argument als *Wert* oder als *Verweis*an eine Prozedur übergeben. Dies wird als *Übergabe Mechanismus*bezeichnet und bestimmt, ob die Prozedur das Programmier Element, das dem Argument zugrunde liegt, im aufrufenden Code ändern kann. Die Prozedur Deklaration bestimmt den Übergabe Mechanismus für jeden Parameter, indem das [ByVal](../../../language-reference/modifiers/byval.md) -oder [ByRef](../../../language-reference/modifiers/byref.md) -Schlüsselwort angegeben wird.  
  
## <a name="distinctions"></a>Besonderheiten  

 Beachten Sie beim Übergeben eines Arguments an eine Prozedur verschiedene Unterschiede, die miteinander interagieren:  
  
- Gibt an, ob das zugrunde liegende Programmier Element änderbar oder nicht änderbar ist.  
  
- Gibt an, ob das Argument selbst änderbar oder nicht änderbar ist.  
  
- Gibt an, ob das Argument als Wert oder als Verweis übermittelt wird.  
  
- Gibt an, ob der Argument Datentyp ein Werttyp oder ein Verweistyp ist.  
  
 Weitere Informationen finden Sie [unter Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md) und [Unterschiede zwischen dem Übergeben eines Arguments als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="choice-of-passing-mechanism"></a>Auswahl des Übergangsmechanismus  

 Sie sollten den Übergabe Mechanismus für jedes Argument sorgfältig auswählen.  
  
- **Schutz**. Bei der Wahl zwischen den beiden Übergabe Mechanismen besteht das wichtigste Kriterium darin, das Aufrufen von Variablen zu ändern. Der Vorteil der Übergabe eines Arguments `ByRef` besteht darin, dass die Prozedur einen Wert an den aufrufenden Code durch dieses Argument zurückgeben kann. Der Vorteil der Übergabe eines Arguments `ByVal` besteht darin, dass eine Variable vor der Änderung durch die Prozedur geschützt wird.  
  
- **Leistung**. Obwohl der Übergabe Mechanismus die Leistung des Codes beeinträchtigen kann, ist der Unterschied in der Regel unbedeutend. Eine Ausnahme besteht darin, dass ein Werttyp erfolgreich ist `ByVal` . In diesem Fall kopiert Visual Basic den gesamten Dateninhalt des Arguments. Daher kann es für einen umfangreichen Werttyp, z. b. eine Struktur, effizienter sein, ihn zu übergeben `ByRef` .  
  
     Bei Verweis Typen wird nur der Zeiger auf die Daten kopiert (vier Bytes auf 32-Bit-Plattformen, 8 Bytes auf 64-Bit-Plattformen). Daher können Sie Argumente des Typs `String` oder `Object` nach Wert übergeben, ohne die Leistung zu beeinträchtigen.  
  
## <a name="determination-of-the-passing-mechanism"></a>Bestimmung des Übergabe Mechanismus  

 Die Prozedur Deklaration gibt den Übergabe Mechanismus für die einzelnen Parameter an. Der Aufruf Code kann einen Mechanismus nicht überschreiben `ByVal` .  
  
 Wenn ein Parameter mit deklariert wird `ByRef` , kann der aufrufende Code den Mechanismus erzwingen, `ByVal` indem er den Argument Namen in Klammern des Aufrufs einschließt. Weitere Informationen finden Sie unter Gewusst [wie: erzwingen, dass ein Argument als Wert weitergegeben wird](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
 Der Standardwert in Visual Basic besteht darin, Argumente als Wert zu übergeben.  
  
## <a name="when-to-pass-an-argument-by-value"></a>Wann ein Argument als Wert übergeben werden soll  
  
- Wenn das aufrufende Code Element, das dem Argument zugrunde liegt, ein nicht änderbares Element ist, deklarieren Sie den entsprechenden Parameter [ByVal](../../../language-reference/modifiers/byval.md). Der Wert eines nicht änderbaren Elements kann durch keinen Code geändert werden.  
  
- Wenn das zugrunde liegende Element geändert werden kann, Sie aber nicht möchten, dass die Prozedur den Wert ändern kann, deklarieren Sie den-Parameter `ByVal` . Nur der aufrufenden Code kann den Wert eines änderbaren Elements ändern, das als Wert übermittelt wurde.  
  
## <a name="when-to-pass-an-argument-by-reference"></a>Wann ein Argument als Verweis übergeben werden soll  
  
- Wenn die Prozedur eine echte Notwendigkeit hat, das zugrunde liegende Element im aufrufenden Code zu ändern, deklarieren Sie den entsprechenden Parameter [ByRef](../../../language-reference/modifiers/byref.md).  
  
- Wenn die korrekte Ausführung des Codes von der Prozedur abhängig ist, die das zugrunde liegende Element im aufrufenden Code ändert, deklarieren Sie den-Parameter `ByRef` . Wenn Sie Sie als Wert übergeben, oder wenn der aufrufende Code den `ByRef` Übergabe Mechanismus überschreibt, indem Sie das Argument in Klammern einschließen, kann der Prozedur Aufruf unerwartete Ergebnisse verursachen.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  

 Im folgenden Beispiel wird veranschaulicht, wann Argumente als Wert übergeben werden und wann Sie als Verweis übergeben werden. Die Prozedur `Calculate` verfügt über einen `ByVal` -Parameter und einen- `ByRef` Parameter. Bei Angabe eines Zinssatz, `rate` von und einer Summe von Money, `debt` ist die Aufgabe der Prozedur das Berechnen eines neuen Werts für das `debt` Ergebnis der Anwendung des Zinssatz auf den ursprünglichen Wert von `debt` . Da `debt` ein `ByRef` Parameter ist, wird der neue Gesamtwert im Wert des-Arguments im aufrufenden Code widergespiegelt, der entspricht `debt` . `rate`Der Parameter ist ein `ByVal` Parameter, da `Calculate` seinen Wert nicht ändern sollte.  
  
### <a name="code"></a>Code  

 [!code-vb[VbVbcnProcedures#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class2.vb#74)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweisen](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Vorgehensweise: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Vorgehensweise: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)
- [Vorgehensweise: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Vorgehensweise: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)
- [Wert- und Verweistypen](../data-types/value-types-and-reference-types.md)
