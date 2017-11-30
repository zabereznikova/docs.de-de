---
title: Take-Klausel (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ee289a24c15226126a526af116ed53b4a9055b35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="take-clause-visual-basic"></a>Take-Klausel (Visual Basic)
Gibt eine angegebene Anzahl von zusammenhängenden Elementen vom Anfang einer Auflistung zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
Take count  
```  
  
## <a name="parts"></a>Teile  
 `count`  
 Erforderlich. Ein Wert oder einen Ausdruck, der die Anzahl der Elemente der Sequenz zurückzugebenden ergibt.  
  
## <a name="remarks"></a>Hinweise  
 Die `Take` -Klausel bewirkt, dass eine Abfrage an eine angegebene Anzahl von zusammenhängenden Elementen vom Anfang einer Ergebnisliste enthalten. Die Anzahl der einzuschließenden Elemente gemäß der `count` Parameter.  
  
 Sie können die `Take` -Klausel mit der `Skip` -Klausel, um einen Datenbereich aus einem beliebigen Abschnitt einer Abfrage zurückzugeben. Übergeben Sie den Index des ersten Elements des Bereichs, der zu diesem Zweck die `Skip` -Klausel und die Größe des Bereichs, der die `Take` Klausel. In diesem Fall die `Take` -Klausel muss angegeben werden, nachdem die `Skip` Klausel.  
  
 Bei Verwendung der `Take` -Klausel einer Abfrage, Sie müssen auch sicherstellen, dass die Ergebnisse in einer Reihenfolge zurückgegeben werden, die es ermöglichen, wird die `Take` -Klausel, um die gewünschten Ergebnisse einschließen. Weitere Informationen zum Sortieren von Abfrageergebnissen finden Sie unter [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Sie können die `TakeWhile` -Klausel, um anzugeben, dass nur bestimmte Elemente zurückgegeben werden, abhängig von einer angegebenen Bedingung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird mit der `Take` -Klausel zusammen mit der `Skip` -Klausel, um Daten aus einer Abfrage in Seiten zurückgegeben. Die GetCustomers-Funktion verwendet die `Skip` -Klausel, um die Kunden in der Liste zu umgehen, bis die angegebenen Wert und verwendet die `Take` -Klausel, um das Zurückgeben einer Seite mit Kunden, die von diesem Indexwert ab.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Abfragen](../../../visual-basic/language-reference/queries/queries.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Take While-Klausel](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Skip-Klausel](../../../visual-basic/language-reference/queries/skip-clause.md)
