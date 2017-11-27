---
title: Skip-Klausel (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 508f3c094df4c834305bcb4a78223c1cee82b1c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="skip-clause-visual-basic"></a>Skip-Klausel (Visual Basic)
Überspringt eine festgelegte Anzahl von Elementen in einer Auflistung und gibt anschließend die übrigen Elemente zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
Skip count  
```  
  
## <a name="parts"></a>Teile  
 `count`  
 Erforderlich. Ein Wert oder einen Ausdruck, der die Anzahl der Elemente der Sequenz zu überspringenden ergibt.  
  
## <a name="remarks"></a>Hinweise  
 Die `Skip` -Klausel bewirkt, dass eine Abfrage Elemente am Anfang einer Ergebnisliste zu umgehen und die übrigen Elemente zurück. Die Anzahl der zu überspringenden Elemente wird durch identifiziert die `count` Parameter.  
  
 Sie können die `Skip` -Klausel mit der `Take` -Klausel, um einen Datenbereich aus einem beliebigen Abschnitt einer Abfrage zurückzugeben. Übergeben Sie den Index des ersten Elements des Bereichs, der zu diesem Zweck die `Skip` -Klausel und die Größe des Bereichs, der die `Take` Klausel.  
  
 Bei Verwendung der `Skip` -Klausel einer Abfrage, Sie müssen auch sicherstellen, dass die Ergebnisse in einer Reihenfolge zurückgegeben werden, die es ermöglichen, wird die `Skip` -Klausel, um die gewünschten Ergebnisse zu umgehen. Weitere Informationen zum Sortieren von Abfrageergebnissen finden Sie unter [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Sie können die `SkipWhile` -Klausel, um anzugeben, dass nur bestimmte Elemente, abhängig von einer angegebenen Bedingung ignoriert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird mit der `Skip` -Klausel zusammen mit der `Take` -Klausel, um Daten aus einer Abfrage in Seiten zurückgegeben. Die `GetCustomers` Funktion verwendet die `Skip` -Klausel, um die Kunden in der Liste zu umgehen, bis die angegebenen Wert und verwendet die `Take` -Klausel, um das Zurückgeben einer Seite mit Kunden, die von diesem Indexwert ab.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Abfragen](../../../visual-basic/language-reference/queries/queries.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Skip While-Klausel](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Take-Klausel](../../../visual-basic/language-reference/queries/take-clause.md)
