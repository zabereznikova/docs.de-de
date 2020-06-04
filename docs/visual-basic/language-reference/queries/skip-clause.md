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
ms.openlocfilehash: 427d14453260a54bd3f2ab9a8ac75dedacd291f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359657"
---
# <a name="skip-clause-visual-basic"></a>Skip-Klausel (Visual Basic)
Überspringt eine festgelegte Anzahl von Elementen in einer Auflistung und gibt anschließend die übrigen Elemente zurück.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a>Bestandteile  
 `count`  
 Erforderlich. Ein-Wert oder ein Ausdruck, der die Anzahl der zu über springenden Elemente der Sequenz ergibt.  
  
## <a name="remarks"></a>Bemerkungen  
 Die `Skip` -Klausel bewirkt, dass eine Abfrage Elemente am Anfang einer Ergebnisliste umgeht und die restlichen Elemente zurückgibt. Die Anzahl der zu über springenden Elemente wird durch den- `count` Parameter identifiziert.  
  
 Sie können die- `Skip` Klausel mit der- `Take` Klausel verwenden, um einen Datenbereich aus einem beliebigen Segment einer Abfrage zurückzugeben. Übergeben Sie hierzu den Index des ersten Elements des Bereichs an die `Skip` -Klausel und die Größe des Bereichs an die- `Take` Klausel.  
  
 Wenn Sie die- `Skip` Klausel in einer Abfrage verwenden, müssen Sie möglicherweise auch sicherstellen, dass die Ergebnisse in einer Reihenfolge zurückgegeben werden, die die- `Skip` Klausel zum Umgehen der beabsichtigten Ergebnisse ermöglicht. Weitere Informationen zum Sortieren von Abfrage Ergebnissen finden Sie unter [Order By-Klausel](order-by-clause.md).  
  
 Sie können die- `SkipWhile` Klausel verwenden, um anzugeben, dass nur bestimmte Elemente ignoriert werden, abhängig von der angegebenen Bedingung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die- `Skip` Klausel in Verbindung mit der- `Take` Klausel verwendet, um Daten aus einer Abfrage in Seiten zurückzugeben. Die- `GetCustomers` Funktion verwendet die- `Skip` Klausel, um die Kunden in der Liste bis zum bereitgestellten Start Index Wert zu umgehen, und verwendet die- `Take` Klausel, um eine Kundenseite zurückzugeben, beginnend mit diesem Indexwert.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](index.md)
- [SELECT-Klausel](select-clause.md)
- [From-Klausel](from-clause.md)
- [Order By-Klausel](order-by-clause.md)
- [SkipWhile-Klausel](skip-while-clause.md)
- [Take-Klausel](take-clause.md)
