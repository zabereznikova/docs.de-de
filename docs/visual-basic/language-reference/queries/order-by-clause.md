---
title: "Order By Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryOrderBy"
  - "vb.QueryAscending"
  - "vb.QueryDescending"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "queries [Visual Basic], Order By"
  - "Order By clause"
  - "Order By statement"
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Order By Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt die Sortierreihenfolge für ein Abfrageergebnis an.  
  
## Syntax  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## Teile  
 `orderExp1`  
 Erforderlich.  Ein oder mehrere Felder des aktuellen Abfrageergebnisses, die die Reihenfolge der zurückgegebenen Werte angeben.  Die Feldnamen müssen durch Kommas \(,\) voneinander getrennt werden.  Sie können für die Felder mithilfe der Schlüsselwörter `Ascending` oder `Descending` eine aufsteigende bzw. absteigende Reihenfolge festlegen.  Wenn kein `Ascending`\-Schlüsselwort oder `Descending`\-Schlüsselwort angegeben ist, wird standardmäßig die aufsteigende Sortierreihenfolge verwendet.  Die Rangfolge bei Feldern bezüglich der Sortierreihenfolge verläuft von links nach rechts.  
  
## Hinweise  
 Sie können die `Order By`\-Klausel verwenden, um die Ergebnisse einer Abfrage zu sortieren.  Die `Order By`\-Klausel kann ein Ergebnis nur auf Grundlage der Bereichsvariablen für den aktuellen Bereich sortieren.  Beispielsweise wird mit der `Select`\-Klausel ein neuer Bereich in einem Abfrageausdruck mit neuen Iterationsvariablen für diesen Bereich eingeführt.  Bereichsvariablen, die vor einer `Select`\-Klausel in einer Abfrage definiert sind, sind nach der `Select`\-Klausel nicht verfügbar.  Wenn Sie die Reihenfolge der Ergebnisse anhand eines Felds festlegen möchten, das nicht in der `Select`\-Klausel verfügbar ist, muss die `Order By`\-Klausel der `Select`\-Klausel vorangestellt werden.  Dies ist beispielsweise dann notwendig, wenn Sie eine Abfrage nach Feldern sortieren möchten, die nicht als Teil des Ergebnisses zurückgegeben werden.  
  
 Die aufsteigende bzw. absteigende Reihenfolge für ein Feld wird durch die Implementierung der <xref:System.IComparable>\-Schnittstelle für den Datentyp des Felds bestimmt.  Wenn der Datentyp die <xref:System.IComparable>\-Schnittstelle nicht implementiert, wird die Sortierreihenfolge ignoriert.  
  
## Beispiel  
 Der folgende Abfrageausdruck verwendet eine `From`\-Klausel zum Deklarieren einer Bereichsvariablen `book` für die `books`\-Auflistung.  Die `Order By`\-Klausel sortiert das Abfrageergebnis nach Preis in aufsteigender Reihenfolge \(Standard\).  Bücher mit dem gleichen Preis werden nach Titel in aufsteigender Reihenfolge sortiert.  Die `Select`\-Klausel wählt die `Title`\-Eigenschaft und die `Price`\-Eigenschaft als Rückgabewerte der Abfrage.  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## Beispiel  
 Der folgende Abfrageausdruck verwendet die `Order By`\-Klausel zum Sortieren des Abfrageergebnisses nach Preis in absteigender Reihenfolge.  Bücher mit dem gleichen Preis werden nach Titel in aufsteigender Reihenfolge sortiert.  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## Beispiel  
 Der folgende Abfrageausdruck verwendet eine `Select`\-Klausel, um Buchtitel, Preis, Veröffentlichungsdatum und Autor auszuwählen.  Dann werden das `Title`, `Price`, `PublishDate`\-Feld und das `Author`\-Feld der Bereichsvariablen für den neuen Bereich mit Daten gefüllt.  Die `Order By`\-Klausel sortiert die neue Bereichsvariable nach Autorennamen, Buchtitel und Preis.  Jede Spalte wird in der Standardreihenfolge \(aufsteigend\) sortiert.  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)