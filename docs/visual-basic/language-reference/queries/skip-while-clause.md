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
ms.openlocfilehash: 3d6caeb1938e8e53e8ec2575f740cd5e49496f62
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839898"
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
|`expression`|Erforderlich. Ein Ausdruck, der eine Bedingung zum Testen von Elementen für darstellt. Der Ausdruck muss Zurückgeben einer `Boolean` Wert oder eine funktionale Entsprechung wie z. B. eine `Integer` als ausgewertet werden soll eine `Boolean`.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Skip While` -Klausel werden die Elemente am Anfang eines Abfrageergebnisses, bis die angegebene `expression` gibt `false`. Nach dem `expression` gibt `false`, die Abfrage gibt alle übrigen Elemente zurück. Die `expression` wird für die verbleibenden Ergebnisse ignoriert.  
  
 Die `Skip While` Klausel unterscheidet sich von der `Where` -Klausel in, das die `Where` Klausel kann verwendet werden, um alle Elemente aus einer Abfrage, die eine bestimmte Bedingung nicht erfüllen ausgeschlossen. Die `Skip While` -Klausel schließt Weitere Elemente nur bis zum ersten Mal, die die Bedingung nicht erfüllt ist. Die `Skip While` -Klausel ist besonders hilfreich, wenn Sie mit einer sortierten Abfrageergebnis arbeiten.  
  
 Sie können eine bestimmte Anzahl von Ergebnissen zu Beginn eines Abfrageergebnisses umgehen, indem Sie mit der `Skip` Klausel.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die `Skip While` -Klausel, um Ergebnisse zu umgehen, bis der erste Kunde aus den Vereinigten Staaten gefunden wird.  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Skip-Klausel](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Take While-Klausel](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
