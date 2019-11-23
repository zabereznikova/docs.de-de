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
ms.openlocfilehash: 404dd848058f7e5c9bc8a74b6d89df18c6c55fad
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004999"
---
# <a name="where-clause-visual-basic"></a>Where-Klausel (Visual Basic)
Gibt die Filterbedingung für eine Abfrage an.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a>-Komponenten  
 `condition`  
 Erforderlich Ein Ausdruck, der bestimmt, ob die Werte für das aktuelle Element in der Auflistung in der Ausgabe Auflistung enthalten sind. Der Ausdruck muss zu einem `Boolean` Wert oder der Entsprechung eines `Boolean` Werts ausgewertet werden. Wenn die Bedingung als `True`ausgewertet wird, wird das Element in das Abfrageergebnis eingeschlossen. Andernfalls wird das-Element aus dem Abfrageergebnis ausgeschlossen.  
  
## <a name="remarks"></a>Hinweise  
 Mit der `Where`-Klausel können Sie Abfrage Daten filtern, indem Sie nur Elemente auswählen, die bestimmte Kriterien erfüllen. Elemente, deren Werte bewirken, dass die `Where`-Klausel zu `True` ausgewertet wird, sind im Abfrageergebnis enthalten. andere Elemente werden ausgeschlossen. Der Ausdruck, der in einer `Where`-Klausel verwendet wird, muss zu einem `Boolean` oder dem Äquivalent eines `Boolean`ausgewertet werden, z. b. eine ganze Zahl, die `False` ergibt, wenn der Wert 0 (null) ist. Sie können mehrere Ausdrücke in einer `Where`-Klausel kombinieren, indem Sie logische Operatoren wie z. b. `And`, `Or`, `AndAlso`, `OrElse`, `Is`und `IsNot`verwenden.  
  
 Standardmäßig werden Abfrage Ausdrücke erst ausgewertet, wenn auf Sie zugegriffen wird – z. b. Wenn Sie in einer `For` Schleife Daten gebunden oder durchlaufen haben. Folglich wird die `Where`-Klausel erst ausgewertet, wenn auf die Abfrage zugegriffen wird. Wenn Sie Werte außerhalb der Abfrage haben, die in der `Where`-Klausel verwendet werden, stellen Sie sicher, dass der entsprechende Wert in der `Where`-Klausel zum Zeitpunkt der Abfrage Ausführung verwendet wird. Weitere Informationen zur Abfrage Ausführung finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 Sie können Funktionen innerhalb einer `Where`-Klausel aufzurufen, um eine Berechnung oder einen Vorgang für einen Wert aus dem aktuellen Element in der Auflistung auszuführen. Wenn Sie eine Funktion in einer `Where`-Klausel aufrufen, kann dies dazu führen, dass die Abfrage sofort ausgeführt wird, wenn Sie definiert wird, anstatt dass Sie aufgerufen wird. Weitere Informationen zur Abfrage Ausführung finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrage Ausdruck verwendet eine `From`-Klausel, um für jedes `Customer`-Objekt in der `customers` Auflistung eine Bereichs Variable `cust` zu deklarieren. Die `Where`-Klausel verwendet die Range-Variable, um die Ausgabe auf Kunden aus dem angegebenen Bereich zu beschränken. Die `For Each`-Schleife zeigt den Firmennamen für jeden Kunden im Abfrageergebnis an.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die logischen Operatoren `And` und `Or` in der `Where`-Klausel verwendet.  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [For Each...Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
