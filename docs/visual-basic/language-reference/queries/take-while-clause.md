---
title: Take While-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 23b7c84a9f896161a66059fcb1f30753d3b863d5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347108"
---
# <a name="take-while-clause-visual-basic"></a>Take While-Klausel (Visual Basic)
Gibt Elemente in einer Auflistung zurück, solange eine angegebene Bedingung `true` ist, und überspringt dann die übrigen Elemente.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`expression`|Erforderlich Ein Ausdruck, der eine Bedingung darstellt, für die Elemente getestet werden sollen. Der Ausdruck muss einen `Boolean` Wert oder eine funktionale Entsprechung zurückgeben, z. b. eine `Integer`, die als `Boolean`ausgewertet werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Take While`-Klausel schließt Elemente vom Anfang eines Abfrage Ergebnisses ein, bis die angegebene `expression` `false`zurückgibt. Nachdem die `expression` `false`zurückgegeben hat, werden alle verbleibenden Elemente von der Abfrage umgangen. Der `expression` wird für die restlichen Ergebnisse ignoriert.  
  
 Die `Take While`-Klausel unterscheidet sich von der `Where`-Klausel darin, dass die `Where`-Klausel verwendet werden kann, um alle Elemente aus einer Abfrage aufzunehmen, die eine bestimmte Bedingung erfüllen. Die `Take While`-Klausel enthält Elemente nur bis zum ersten Mal, wenn die Bedingung nicht erfüllt wird. Die `Take While`-Klausel ist besonders nützlich, wenn Sie mit einem geordneten Abfrageergebnis arbeiten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die `Take While`-Klausel verwendet, um die Ergebnisse abzurufen, bis der erste Kunde ohne Bestellungen gefunden wird.  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Take-Klausel](../../../visual-basic/language-reference/queries/take-clause.md)
- [Skip While-Klausel](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
