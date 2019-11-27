---
title: Order By-Klausel
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
ms.openlocfilehash: a7104e3dd82ff2dde2911861ce98a7367faf3b25
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350420"
---
# <a name="order-by-clause-visual-basic"></a>ORDER BY-Klausel (Visual Basic)
Gibt die Sortierreihenfolge für ein Abfrageergebnis an.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a>-Komponenten  
 `orderExp1`  
 Erforderlich Ein oder mehrere Felder aus dem aktuellen Abfrageergebnis, die die Reihenfolge der zurückgegebenen Werte bestimmen. Die Feldnamen müssen durch Kommas (,) getrennt werden. Sie können jedes Feld in aufsteigender oder absteigender Reihenfolge mithilfe der Schlüsselwörter `Ascending` oder `Descending` ermitteln. Wenn keine `Ascending` oder `Descending` Schlüsselwort angegeben ist, ist die Standard Sortierreihenfolge aufsteigend. Die Sortier Reihenfolgen Felder haben Vorrang vor von links nach rechts.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `Order By`-Klausel verwenden, um die Ergebnisse einer Abfrage zu sortieren. Die `Order By`-Klausel kann ein Ergebnis nur basierend auf der Bereichs Variablen für den aktuellen Gültigkeitsbereich sortieren. Die `Select`-Klausel führt z. b. einen neuen Bereich in einem Abfrage Ausdruck mit neuen Iterations Variablen für diesen Bereich ein. Bereichs Variablen, die vor einer `Select`-Klausel in einer Abfrage definiert sind, sind nach der `Select`-Klausel nicht verfügbar. Wenn Sie also die Ergebnisse nach einem Feld sortieren möchten, das in der `Select`-Klausel nicht verfügbar ist, müssen Sie die `Order By`-Klausel vor der `Select`-Klausel ablegen. Ein Beispiel hierfür wäre, wenn Sie die Abfrage nach Feldern sortieren möchten, die nicht als Teil des Ergebnisses zurückgegeben werden.  
  
 Die aufsteigende und absteigende Reihenfolge für ein Feld wird durch die Implementierung der <xref:System.IComparable>-Schnittstelle für den Datentyp des Felds bestimmt. Wenn der Datentyp die <xref:System.IComparable>-Schnittstelle nicht implementiert, wird die Sortierreihenfolge ignoriert.  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrage Ausdruck verwendet eine `From`-Klausel, um eine Bereichs Variable `book` für die `books` Collection zu deklarieren. Die `Order By`-Klausel sortiert das Abfrageergebnis nach Preis in aufsteigender Reihenfolge (Standardeinstellung). Bücher mit demselben Preis werden nach Titel in aufsteigender Reihenfolge sortiert. Die `Select`-Klausel wählt die Eigenschaften `Title` und `Price` als die von der Abfrage zurückgegebenen Werte aus.  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrage Ausdruck verwendet die `Order By`-Klausel, um das Abfrageergebnis nach Preis in absteigender Reihenfolge zu sortieren. Bücher mit demselben Preis werden nach Titel in aufsteigender Reihenfolge sortiert.  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrage Ausdruck verwendet eine `Select`-Klausel, um den Buchtitel, den Preis, das Veröffentlichungsdatum und den Autor auszuwählen. Anschließend werden die Felder "`Title`", "`Price`", "`PublishDate`" und "`Author`" der Bereichs Variablen für den neuen Bereich aufgefüllt. Die `Order By`-Klausel ordnet die neue Bereichs Variable nach Autor Name, Titel Titel und Preis an. Jede Spalte wird in der Standard Reihenfolge sortiert (aufsteigend).  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
