---
title: Take-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 25dd06905525a96bc1504f033eb4f19af6d454a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359631"
---
# <a name="take-clause-visual-basic"></a>Take-Klausel (Visual Basic)
Gibt eine angegebene Anzahl von zusammenhängenden Elementen vom Anfang einer Auflistung zurück.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Take count  
```  
  
## <a name="parts"></a>Bestandteile  
 `count`  
 Erforderlich. Ein-Wert oder ein Ausdruck, der die Anzahl der Elemente der Sequenz ergibt, die zurückgegeben werden soll.  
  
## <a name="remarks"></a>Bemerkungen  
 Die- `Take` Klausel bewirkt, dass eine Abfrage eine angegebene Anzahl von zusammenhängenden Elementen ab dem Anfang einer Ergebnisliste enthält. Die Anzahl der einzuschließenden Elemente wird durch den- `count` Parameter angegeben.  
  
 Sie können die- `Take` Klausel mit der- `Skip` Klausel verwenden, um einen Datenbereich aus einem beliebigen Segment einer Abfrage zurückzugeben. Übergeben Sie hierzu den Index des ersten Elements des Bereichs an die `Skip` -Klausel und die Größe des Bereichs an die- `Take` Klausel. In diesem Fall muss die- `Take` Klausel nach der-Klausel angegeben werden `Skip` .  
  
 Wenn Sie die- `Take` Klausel in einer Abfrage verwenden, müssen Sie möglicherweise auch sicherstellen, dass die Ergebnisse in einer Reihenfolge zurückgegeben werden, in der die- `Take` Klausel die beabsichtigten Ergebnisse einbeziehen kann. Weitere Informationen zum Sortieren von Abfrage Ergebnissen finden Sie unter [Order By-Klausel](order-by-clause.md).  
  
 Sie können die- `TakeWhile` Klausel verwenden, um anzugeben, dass nur bestimmte Elemente zurückgegeben werden sollen, abhängig von der angegebenen Bedingung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die- `Take` Klausel in Verbindung mit der- `Skip` Klausel verwendet, um Daten aus einer Abfrage in Seiten zurückzugeben. Die GetCustomers-Funktion verwendet die- `Skip` Klausel, um die Kunden in der Liste bis zum bereitgestellten Start Index Wert zu umgehen, und verwendet die- `Take` Klausel, um eine Seite mit Kunden zurückzugeben, beginnend mit diesem Indexwert.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](index.md)
- [SELECT-Klausel](select-clause.md)
- [From-Klausel](from-clause.md)
- [Order By-Klausel](order-by-clause.md)
- [TakeWhile-Klausel](take-while-clause.md)
- [Skip-Klausel](skip-clause.md)
