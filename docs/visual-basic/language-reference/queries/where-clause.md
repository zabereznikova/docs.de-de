---
title: Where-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: b80bb047551dee8ab23cfac06b961996992d69b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359540"
---
# <a name="where-clause-visual-basic"></a>Where-Klausel (Visual Basic)
Gibt die Filterbedingung für eine Abfrage an.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a>Bestandteile  
 `condition`  
 Erforderlich. Ein Ausdruck, der bestimmt, ob die Werte für das aktuelle Element in der Auflistung in der Ausgabe Auflistung enthalten sind. Der Ausdruck muss zu einem- `Boolean` Wert oder dem-Äquivalent eines-Werts ausgewertet werden `Boolean` . Wenn die Bedingung ergibt `True` , wird das-Element in das Abfrageergebnis eingeschlossen. andernfalls wird das-Element aus dem Abfrageergebnis ausgeschlossen.  
  
## <a name="remarks"></a>Bemerkungen  
 Mit der- `Where` Klausel können Sie Abfrage Daten filtern, indem Sie nur Elemente auswählen, die bestimmte Kriterien erfüllen. Elemente, deren Werte bewirken, dass die- `Where` Klausel ausgewertet `True` wird, werden in das Abfrageergebnis eingeschlossen. andere Elemente werden ausgeschlossen. Der Ausdruck, der in einer-Klausel verwendet wird, `Where` muss zu einer `Boolean` oder der-Entsprechung von ausgewertet `Boolean` werden, z. b. eine ganze Zahl, die ergibt, `False` Wenn der Wert NULL ist. Sie können mehrere Ausdrücke in einer- `Where` Klausel kombinieren, indem Sie logische Operatoren wie `And` , `Or` , `AndAlso` , `OrElse` , `Is` und verwenden `IsNot` .  
  
 Standardmäßig werden Abfrage Ausdrücke erst ausgewertet, wenn auf Sie zugegriffen wird – z. b. Wenn Sie in einer-Schleife Daten gebunden oder durchlaufen haben `For` . Folglich wird die- `Where` Klausel erst ausgewertet, wenn auf die Abfrage zugegriffen wird. Wenn Sie Werte außerhalb der Abfrage haben, die in der-Klausel verwendet werden `Where` , stellen Sie sicher, dass der entsprechende Wert in der- `Where` Klausel zum Zeitpunkt der Abfrage Ausführung verwendet wird. Weitere Informationen zur Abfrage Ausführung finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 Sie können Funktionen innerhalb einer- `Where` Klausel aufzurufen, um eine Berechnung oder einen Vorgang für einen Wert aus dem aktuellen Element in der Auflistung auszuführen. Das Aufrufen einer Funktion in einer- `Where` Klausel kann bewirken, dass die Abfrage sofort ausgeführt wird, wenn Sie definiert wird, und nicht, wenn darauf zugegriffen wird. Weitere Informationen zur Abfrage Ausführung finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrage Ausdruck verwendet eine- `From` Klausel, um eine Bereichs Variable `cust` für jedes `Customer` Objekt in der Auflistung zu deklarieren `customers` . Die- `Where` Klausel verwendet die Range-Variable, um die Ausgabe auf Kunden aus dem angegebenen Bereich zu beschränken. In der- `For Each` Schleife wird der Firmenname für jeden Kunden im Abfrageergebnis angezeigt.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden `And` die `Or` logischen Operatoren und in der- `Where` Klausel verwendet.  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](index.md)
- [From-Klausel](from-clause.md)
- [SELECT-Klausel](select-clause.md)
- [For Each...Next-Anweisung](../statements/for-each-next-statement.md)
