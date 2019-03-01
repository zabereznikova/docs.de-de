---
title: Take While-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: f7e0587d7737d99d48fcc9cd4a102e78248a55e5
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979933"
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
|`expression`|Erforderlich. Ein Ausdruck, der eine Bedingung zum Testen von Elementen für darstellt. Der Ausdruck muss Zurückgeben einer `Boolean` Wert oder eine funktionale Entsprechung wie z. B. eine `Integer` als ausgewertet werden soll eine `Boolean`.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Take While` -Klausel enthält Elementen ab dem Anfang eines Abfrageergebnisses, bis die angegebene `expression` gibt `false`. Nach der `expression` gibt `false`, die Abfrage werden alle verbleibenden Elemente zu umgehen. Die `expression` wird für die verbleibenden Ergebnisse ignoriert.  
  
 Die `Take While` Klausel unterscheidet sich von der `Where` -Klausel in, das die `Where` -Klausel kann verwendet werden, um alle Elemente aus einer Abfrage enthalten, die eine bestimmte Bedingung erfüllen. Die `Take While` -Klausel enthält Elemente nur bis zum ersten Mal, die die Bedingung nicht erfüllt ist. Die `Take While` -Klausel ist besonders hilfreich, wenn Sie mit einer sortierten Abfrageergebnis arbeiten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die `Take While` -Klausel, um die Ergebnisse abzurufen, bis die erste Kunden ohne Bestellungen gefunden wird.  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch
- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Take-Klausel](../../../visual-basic/language-reference/queries/take-clause.md)
- [Skip While-Klausel](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
