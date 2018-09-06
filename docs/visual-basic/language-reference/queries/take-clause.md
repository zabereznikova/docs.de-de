---
title: Take-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: bfaccf470d93a6a72451e7ad8b41e8dbb1171c71
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856572"
---
# <a name="take-clause-visual-basic"></a>Take-Klausel (Visual Basic)
Gibt eine angegebene Anzahl von zusammenhängenden Elementen vom Anfang einer Auflistung zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
Take count  
```  
  
## <a name="parts"></a>Teile  
 `count`  
 Erforderlich. Ein Wert oder ein Ausdruck, der die Anzahl der Elemente der Sequenz zurück, die ausgewertet wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `Take` -Klausel bewirkt, dass eine Abfrage, um eine angegebene Anzahl von zusammenhängenden Elementen ab dem Anfang einer Ergebnisliste enthalten. Die Anzahl der einzuschließenden Elemente wird angegeben, durch die `count` Parameter.  
  
 Können Sie die `Take` -Klausel mit der `Skip` -Klausel, um einen Bereich von Daten aus jedem Segment einer Abfrage zurückgeben. Dazu übergeben Sie den Index des ersten Elements des Bereichs, der die `Skip` -Klausel und die Größe des Bereichs, der die `Take` Klausel. In diesem Fall die `Take` -Klausel muss angegeben werden, nachdem die `Skip` Klausel.  
  
 Bei Verwendung der `Take` -Klausel in einer Abfrage, Sie müssen auch sicherstellen, dass die Ergebnisse in der Reihenfolge zurückgegeben werden, mit denen die `Take` -Klausel, um die gewünschten Ergebnisse enthalten. Weitere Informationen zum Sortieren von Abfrageergebnissen finden Sie unter [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Sie können die `TakeWhile` Klausel, um anzugeben, dass nur bestimmte Elemente zurückgegeben werden, je nach einer angegebenen Bedingung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die `Take` -Klausel zusammen mit den `Skip` -Klausel zur Rückgabe von Daten aus einer Abfrage in Seiten. Die GetCustomers-Funktion verwendet die `Skip` -Klausel, um die Kunden in der Liste zu umgehen, bis die angegebenen Wert und verwendet die `Take` -Klausel, um eine Seite mit Kunden, die von diesem Indexwert zurück.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Abfragen](../../../visual-basic/language-reference/queries/index.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Take While-Klausel](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Skip-Klausel](../../../visual-basic/language-reference/queries/skip-clause.md)
