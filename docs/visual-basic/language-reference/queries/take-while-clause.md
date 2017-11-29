---
title: Take While-Klausel (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c8add6c55bb9353bac3489e68f497cb32785aad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="take-while-clause-visual-basic"></a>Take While-Klausel (Visual Basic)
Gibt Elemente in einer Auflistung zurück, solange eine angegebene Bedingung `true` ist, und überspringt dann die übrigen Elemente.  
  
## <a name="syntax"></a>Syntax  
  
```  
Take While expression  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`expression`|Erforderlich. Ein Ausdruck, der eine zu testende Bedingung an Elementen für darstellt. Der Ausdruck muss zurückgeben eine `Boolean` Wert oder eine funktionell gleichwertig, wie z. B. ein `Integer` als ausgewertet werden eine `Boolean`.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Take While` -Klausel enthält Elemente vom Beginn eines Abfrageergebnisses, bis die angegebene `expression` gibt `false`. Nach der `expression` gibt `false`, die Abfrage werden alle verbleibenden Elemente zu umgehen. Die `expression` wird für die restlichen Ergebnisse ignoriert.  
  
 Die `Take While` Klausel unterscheidet sich von der `Where` -Klausel, die die `Where` -Klausel kann verwendet werden, um alle Elemente aus einer Abfrage enthalten, die eine bestimmte Bedingung erfüllen. Die `Take While` -Klausel enthält Elemente nur bis zum ersten Mal, die die Bedingung nicht erfüllt wird. Die `Take While` -Klausel ist besonders hilfreich bei der Arbeit mit einer sortierten Abfrageergebnis.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird mit der `Take While` -Klausel, um die Ergebnisse abzurufen, bis die erste Kunden ohne Bestellungen gefunden wird.  
  
 [!code-vb[VbSimpleQuerySamples#2](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-while-clause_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Abfragen](../../../visual-basic/language-reference/queries/queries.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Take-Klausel](../../../visual-basic/language-reference/queries/take-clause.md)  
 [Skip While-Klausel](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
