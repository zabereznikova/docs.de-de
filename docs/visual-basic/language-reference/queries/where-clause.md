---
title: Where-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 0b61a52a366fb37a0834c9223bc8b7f099354d16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="where-clause-visual-basic"></a>Where-Klausel (Visual Basic)
Gibt die filterbedingung für eine Abfrage an.  
  
## <a name="syntax"></a>Syntax  
  
```  
Where condition  
```  
  
## <a name="parts"></a>Teile  
 `condition`  
 Erforderlich. Ein Ausdruck, der bestimmt, ob die Werte für das aktuelle Element in der Auflistung in der Output-Auflistung enthalten sind. Der Ausdruck ausgewertet werden muss, um eine `Boolean` Wert oder das Äquivalent zu einer `Boolean` Wert. Wenn die Bedingung ergibt `True`, das Element im Abfrageergebnis enthalten, andernfalls wird das Element aus dem Abfrageergebnis ausgeschlossen.  
  
## <a name="remarks"></a>Hinweise  
 Die `Where` -Klausel ermöglicht es Ihnen, Filtern Abfragen von Daten durch Auswahl nur Elemente, die bestimmte Kriterien erfüllen. Elemente, deren Werte bewirken, dass, die `Where` -Klausel, um ergeben `True` sind in den Abfrageergebnissen; enthalten andere Elemente ausgeschlossen werden. Der Ausdruck, der verwendet wird eine `Where` Klausel ergeben muss eine `Boolean` oder das Äquivalent zu einer `Boolean`, z. B. eine ganze Zahl, der ergibt `False` Wenn der Wert 0 (null) ist. Sie können mehrere Ausdrücke in kombinieren einer `Where` -Klausel, indem Sie logische Operatoren, wie z. B. `And`, `Or`, `AndAlso`, `OrElse`, `Is`, und `IsNot`.  
  
 Standardmäßig Abfrageausdrücke werden erst ausgewertet, darauf zugegriffen werden – z. B. Wenn sie sind von datengebundenen oder durchlaufen in einem `For` Schleife. Daher die `Where` -Klausel wird nicht ausgewertet werden, bis die Abfrage zugegriffen wird. Haben die Werte, die außerhalb der Abfrage, die in verwendet werden die `Where` -Klausel, stellen Sie sicher, dass der richtige Wert, in verwendet wird der `Where` Klausel, die zum Zeitpunkt der Ausführung der Abfrage. Weitere Informationen zur Ausführung von Abfragen finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 Sie können Funktionen aufrufen einer `Where` -Klausel zum Ausführen einer Berechnung oder einem Vorgang einen Wert aus dem aktuellen Element in der Auflistung. Aufrufen einer Funktion in einer `Where` -Klausel kann dazu führen, dass die Abfrage ausgeführt werden, sofort Wenn sie anstelle von definiert wird, wenn darauf zugegriffen wird. Weitere Informationen zur Ausführung von Abfragen finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="example"></a>Beispiel  
 Die folgende Abfrage Ausdruck verwendet eine `From` -Klausel, um eine Bereichsvariable deklarieren `cust` für jede `Customer` Objekt in der `customers` Auflistung. Die `Where` -Klausel verwendet die Bereichsvariable, um die Ausgabe auf Kunden aus den angegebenen Bereich zu beschränken. Die `For Each` Schleife der Firmenname für jeden Kunden in den Abfrageergebnissen angezeigt.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird `And` und `Or` logische Operatoren in der `Where` Klausel.  
  
 [!code-vb[VbSimpleQuerySamples#31](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Abfragen](../../../visual-basic/language-reference/queries/queries.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)  
 [For Each...Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
