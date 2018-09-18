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
ms.openlocfilehash: d4abb5f0b75ae4069c1dbe695a5c810b1f7aa6e1
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46004277"
---
# <a name="order-by-clause-visual-basic"></a>ORDER BY-Klausel (Visual Basic)
Gibt die Sortierreihenfolge für eine Abfrage an.  
  
## <a name="syntax"></a>Syntax  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a>Teile  
 `orderExp1`  
 Erforderlich. Ein oder mehrere Felder aus dem aktuellen Abfrageergebnis, die identifizieren, wie Sie die Reihenfolge der zurückgegebenen Werte. Die Feldnamen müssen durch Kommas (,) getrennt werden. Sie können jedes Felds identifizieren, als sortiert in aufsteigender oder absteigender Reihenfolge unter Verwendung der `Ascending` oder `Descending` Schlüsselwörter. Wenn kein `Ascending` oder `Descending` -Schlüsselwort angegeben ist, die die Sortierreihenfolge ist Aufsteigend. Die Felder werden die Rangfolge von links nach rechts angegeben.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `Order By` -Klausel zum Sortieren der Ergebnisse einer Abfrage. Die `Order By` -Klausel kann nur basierend auf der die Bereichsvariable für den aktuellen Bereich sortieren. Z. B. die `Select` Klausel führt einen neuen Bereich in einem Abfrageausdruck mit neuen Iterationsvariablen für diesen Bereich. Bereichsvariablen, die definiert, bevor eine `Select` -Klausel in einer Abfrage sind nicht verfügbar, nachdem die `Select` Klausel. Aus diesem Grund sollten Sie die Ergebnisse nach einem Feld zu sortieren, die in nicht verfügbar ist die `Select` -Klausel, müssen Sie setzen das `Order By` -Klausel, bevor die `Select` Klausel. Ein Beispiel wenn Sie dazu müssten ist, wenn eine Abfrage nach Feldern zu sortieren, die nicht als Teil des Ergebnisses zurückgegeben werden sollen.  
  
 Auf- und absteigender Reihenfolge aus, für ein Feld von der Implementierung der bestimmt wird die <xref:System.IComparable> Schnittstelle für den Datentyp des Felds. Wenn der Datentyp nicht implementiert die <xref:System.IComparable> -Schnittstelle, die Sortierreihenfolge wird ignoriert.  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrageausdruck verwendet eine `From` -Klausel, um eine Bereichsvariable deklarieren `book` für die `books` Auflistung. Die `Order By` -Klausel sortiert das Resultset der Abfrage nach Preis in aufsteigender Reihenfolge (Standard). Bücher mit den gleichen Preis sind nach Titel in aufsteigender Reihenfolge sortiert. Die `Select` -Klausel wählt die `Title` und `Price` Eigenschaften wie die von der Abfrage zurückgegebenen Werte.  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrageausdruck verwendet die `Order By` -Klausel, um das Ergebnis der Abfrage nach Preis in absteigender Reihenfolge zu sortieren. Bücher mit den gleichen Preis sind nach Titel in aufsteigender Reihenfolge sortiert.  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrageausdruck verwendet eine `Select` -Klausel, um Wählen Sie den Titel, Preis, Veröffentlichungsdatum und erstellen. Dann füllt es die `Title`, `Price`, `PublishDate`, und `Author` Felder die Bereichsvariable für den neuen Bereich. Die `Order By` -Klausel sortiert die neue Bereichsvariable, die vom Autorenname, Titel und Preis. Jede Spalte ist in der Standardreihenfolge (in aufsteigender Reihenfolge) sortiert.  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Abfragen](../../../visual-basic/language-reference/queries/index.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
