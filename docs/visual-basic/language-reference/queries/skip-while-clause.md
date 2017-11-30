---
title: Skip While-Klausel (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f447a6d9b2eb58fa546ced6c96b987caf68fb3e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="skip-while-clause-visual-basic"></a>Skip While-Klausel (Visual Basic)
Überspringt Elemente in einer Auflistung, solange eine angegebene Bedingung `true` ist, und gibt anschließend die übrigen Elemente zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`expression`|Erforderlich. Ein Ausdruck, der eine zu testende Bedingung an Elementen für darstellt. Der Ausdruck muss zurückgeben eine `Boolean` Wert oder eine funktionell gleichwertig, wie z. B. ein `Integer` als ausgewertet werden eine `Boolean`.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Skip While` Klausel umgeht Elemente vom Anfang bis zum angegebenen eines Abfrageergebnisses `expression` gibt `false`. Nach dem `expression` gibt `false`, die Abfrage gibt alle übrigen Elemente zurück. Die `expression` wird für die restlichen Ergebnisse ignoriert.  
  
 Die `Skip While` Klausel unterscheidet sich von der `Where` -Klausel, die die `Where` -Klausel kann verwendet werden, sollen alle Elemente aus einer Abfrage, die nicht auf eine bestimmte Bedingung erfüllen. Die `Skip While` -Klausel schließt Elemente nur bis zum ersten Mal, die die Bedingung nicht erfüllt wird. Die `Skip While` -Klausel ist besonders hilfreich bei der Arbeit mit einer sortierten Abfrageergebnis.  
  
 Sie können eine bestimmte Anzahl von Ergebnissen zu Beginn eines Abfrageergebnisses umgehen, indem Sie mit der `Skip` Klausel.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird mit der `Skip While` -Klausel, um Ergebnisse zu umgehen, bis die erste Kunden aus den USA gefunden wird.  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Abfragen](../../../visual-basic/language-reference/queries/queries.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Skip-Klausel](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Take While-Klausel](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
