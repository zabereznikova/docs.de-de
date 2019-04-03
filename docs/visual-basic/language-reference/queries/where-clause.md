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
ms.openlocfilehash: 5632e69039baebb3d1f1fd90c04586d9e50fe40f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834503"
---
# <a name="where-clause-visual-basic"></a>Where-Klausel (Visual Basic)
Gibt die filterbedingung für eine Abfrage an.  
  
## <a name="syntax"></a>Syntax  
  
```  
Where condition  
```  
  
## <a name="parts"></a>Teile  
 `condition`  
 Erforderlich. Ein Ausdruck, der bestimmt, ob die Werte für das aktuelle Element in der Auflistung in der Output-Auflistung enthalten sind. Muss der Ausdruck ausgewertet, um eine `Boolean` Wert oder die Darstellung einer `Boolean` Wert. Wenn das Ergebnis der bedingungsauswertung `True`, das Element im Resultset Abfrage enthalten, andernfalls das Element wird aus dem Abfrageergebnis ausgeschlossen.  
  
## <a name="remarks"></a>Hinweise  
 Die `Where` -Klausel ermöglichen es Ihnen, Abfragen von Daten zu filtern, dazu nur Elemente, die bestimmte Kriterien erfüllen. Elemente, deren Werte bewirken, dass, die `Where` Klausel ergibt `True` befinden sich im Resultset Abfrage; andere Elemente ausgeschlossen werden. Der Ausdruck, der verwendet wird eine `Where` Klausel ergeben muss eine `Boolean` oder die Entsprechung von einer `Boolean`, z. B. eine ganze Zahl, der ergibt `False` Wenn der Wert 0 (null) ist. Sie können in mehrere Ausdrücke kombinieren einer `Where` Klausel, indem Sie logische Operatoren wie z. B. `And`, `Or`, `AndAlso`, `OrElse`, `Is`, und `IsNot`.  
  
 In der Standardeinstellung Abfrageausdrücke werden erst ausgewertet, darauf zugegriffen wird, z. B. Wenn sie sind datengebunden oder durchlaufen in einer `For` Schleife. Daher die `Where` Klausel wird nicht ausgewertet, bis die Abfrage zugegriffen wird. Wenn Sie die Werte für die Abfrage, die verwendet werden extern haben die `Where` -Klausel, stellen Sie sicher, dass der entsprechende Wert, in verwendet wird der `Where` Klausel, die zum Zeitpunkt der Ausführung der Abfrage. Weitere Informationen zur Ausführung von Abfragen finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 Sie können Funktionen aufrufen einer `Where` -Klausel, um eine Berechnung oder Operation auf einen Wert aus dem aktuellen Element in der Auflistung ausführen. Aufrufen einer Funktion in einer `Where` Klausel kann dazu führen, dass die Abfrage ausgeführt werden, sofort wenn er nicht definiert wird, wenn darauf zugegriffen wird. Weitere Informationen zur Ausführung von Abfragen finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrageausdruck verwendet eine `From` -Klausel, um eine Bereichsvariable deklarieren `cust` für jede `Customer` -Objekt in der `customers` Auflistung. Die `Where` -Klausel verwendet die Bereichsvariable, um die Ausgabe auf Kunden aus den angegebenen Bereich zu beschränken. Die `For Each` -Schleife zeigt den Firmennamen für jeden Kunden in den Abfrageergebnissen.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird `And` und `Or` logische Operatoren in der `Where` Klausel.  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [For Each...Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
