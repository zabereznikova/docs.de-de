---
title: Skip-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: c582b014bad4fa8fa3165d2b756f4bc955840cfc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349657"
---
# <a name="skip-clause-visual-basic"></a>Skip-Klausel (Visual Basic)
Überspringt eine festgelegte Anzahl von Elementen in einer Auflistung und gibt anschließend die übrigen Elemente zurück.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a>-Komponenten  
 `count`  
 Erforderlich Ein-Wert oder ein Ausdruck, der die Anzahl der zu über springenden Elemente der Sequenz ergibt.  
  
## <a name="remarks"></a>Hinweise  
 Die `Skip`-Klausel bewirkt, dass eine Abfrage Elemente am Anfang einer Ergebnisliste umgeht und die restlichen Elemente zurückgibt. Die Anzahl der zu über springenden Elemente wird durch den `count`-Parameter identifiziert.  
  
 Sie können die `Skip`-Klausel mit der `Take`-Klausel verwenden, um einen Datenbereich aus einem beliebigen Segment einer Abfrage zurückzugeben. Übergeben Sie hierzu den Index des ersten Elements des Bereichs an die `Skip`-Klausel und die Größe des Bereichs an die `Take`-Klausel.  
  
 Wenn Sie die `Skip`-Klausel in einer Abfrage verwenden, müssen Sie möglicherweise auch sicherstellen, dass die Ergebnisse in einer Reihenfolge zurückgegeben werden, die die `Skip`-Klausel zum Umgehen der beabsichtigten Ergebnisse ermöglicht. Weitere Informationen zum Sortieren von Abfrage Ergebnissen finden Sie unter [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Sie können die `SkipWhile`-Klausel verwenden, um anzugeben, dass in Abhängigkeit von einer angegebenen Bedingung nur bestimmte Elemente ignoriert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die `Skip`-Klausel in Verbindung mit der `Take`-Klausel verwendet, um Daten aus einer Abfrage in Seiten zurückzugeben. Die `GetCustomers`-Funktion verwendet die `Skip`-Klausel, um die Kunden in der Liste bis zum bereitgestellten Start Index Wert zu umgehen, und verwendet die `Take`-Klausel, um eine Kundenseite zurückzugeben, beginnend mit diesem Indexwert.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Skip While-Klausel](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Take-Klausel](../../../visual-basic/language-reference/queries/take-clause.md)
