---
title: Skip While-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 9d95dc4a9f61a9ec3a50f9d594b31d673c2d3764
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602018"
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
