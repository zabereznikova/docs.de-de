---
title: ORDER BY-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
ms.openlocfilehash: 7c60156ee81618530b42d5f61dbcac6f59c4f675
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604119"
---
# <a name="order-by-clause-visual-basic"></a>ORDER BY-Klausel (Visual Basic)
Gibt die Sortierreihenfolge für ein Abfrageergebnis an.  
  
## <a name="syntax"></a>Syntax  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a>Teile  
 `orderExp1`  
 Erforderlich. Ein oder mehrere Felder aus dem aktuellen Abfrageergebnis, die bestimmen, wie die Reihenfolge der zurückgegebenen Werte werden. Die Feldnamen müssen durch Kommas (,) getrennt werden. Bestimmen Sie jedes Feld als sortiert in aufsteigender oder absteigender Reihenfolge unter Verwendung der `Ascending` oder `Descending` Schlüsselwörter. Wenn kein `Ascending` oder `Descending` -Schlüsselwort angegeben wird, wird eine aufsteigende die Standardsortierreihenfolge verwendet. Die Reihenfolge Sortierfelder erhalten Vorrang von links nach rechts.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `Order By` -Klausel zum Sortieren der Ergebnisse einer Abfrage. Die `Order By` -Klausel kann nur ein Ergebnis auf Grundlage der Bereichsvariablen für den aktuellen Bereich sortieren. Z. B. die `Select` -Klausel führt einen neuen Bereich in einem Abfrageausdruck mit neuen Iterationsvariablen für diesen Bereich. Bereichsvariablen, die definiert sind, bevor eine `Select` -Klausel in einer Abfrage sind nicht verfügbar, nachdem die `Select` Klausel. Aus diesem Grund sollten Sie die Ergebnisse nach einem Feld zu sortieren, die in nicht verfügbar ist die `Select` -Klausel, müssen Sie Ablegen der `Order By` -Klausel, bevor die `Select` Klausel. Ein Beispiel wenn Sie dazu müssten ist beim Sortieren der Abfrage nach Feldern, die nicht als Teil des Resultsets zurückgegeben werden sollen.  
  
 Auf- und absteigenden Reihenfolge für ein Feld wird durch die Implementierung von bestimmt die <xref:System.IComparable> Schnittstelle für den Datentyp des Felds. Wenn der Datentyp nicht implementiert die <xref:System.IComparable> -Schnittstelle, die Sortierreihenfolge wird ignoriert.  
  
## <a name="example"></a>Beispiel  
 Die folgende Abfrage Ausdruck verwendet eine `From` -Klausel, um eine Bereichsvariable deklarieren `book` für die `books` Auflistung. Die `Order By` -Klausel sortiert das Ergebnis der Abfrage nach dem Preis in aufsteigender Reihenfolge (Standard). Bücher mit dem gleichen Preis werden nach Titel in aufsteigender Reihenfolge sortiert. Die `Select` -Klausel wählt die `Title` und `Price` Eigenschaften als die von der Abfrage zurückgegebenen Werte.  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Die folgende Abfrage verwendet die `Order By` -Klausel, um das Ergebnis der Abfrage nach dem Preis in absteigender Reihenfolge zu sortieren. Bücher mit dem gleichen Preis werden nach Titel in aufsteigender Reihenfolge sortiert.  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Die folgende Abfrage Ausdruck verwendet eine `Select` -Klausel, um die Buchtitel wählen, Preis, Veröffentlichungsdatum und erstellen. Füllt dann die `Title`, `Price`, `PublishDate`, und `Author` Felder der Bereichsvariablen für den neuen Bereich. Die `Order By` -Klausel sortiert die neue Bereichsvariable durch den Namen des Autors, Buchtitel und Preis. Jede Spalte wird in die Standardreihenfolge (aufsteigend) sortiert.  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Abfragen](../../../visual-basic/language-reference/queries/queries.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
