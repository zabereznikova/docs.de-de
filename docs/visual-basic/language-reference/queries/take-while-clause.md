---
title: TakeWhile-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 4b6133efdbd9c46ab85201ad454671e5538b6a81
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359579"
---
# <a name="take-while-clause-visual-basic"></a>Take While-Klausel (Visual Basic)
Gibt Elemente in einer Auflistung zurück, solange eine angegebene Bedingung `true` ist, und überspringt dann die übrigen Elemente.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`expression`|Erforderlich. Ein Ausdruck, der eine Bedingung darstellt, für die Elemente getestet werden sollen. Der Ausdruck muss einen `Boolean` Wert oder eine funktionale Entsprechung zurückgeben, z. b. eine, die `Integer` als ausgewertet wird `Boolean` .|  
  
## <a name="remarks"></a>Bemerkungen  
 Die- `Take While` Klausel schließt Elemente vom Anfang eines Abfrage Ergebnisses ein, bis die angegebene `expression` zurückgibt `false` . Nach dem `expression` zurückkehren `false` werden alle verbleibenden Elemente von der Abfrage umgangen. Der `expression` wird für die restlichen Ergebnisse ignoriert.  
  
 Die- `Take While` Klausel unterscheidet sich von der- `Where` Klausel darin, dass die- `Where` Klausel verwendet werden kann, um alle Elemente aus einer Abfrage aufzunehmen, die eine bestimmte Bedingung erfüllen. Die- `Take While` Klausel enthält Elemente nur bis zum ersten Mal, wenn die Bedingung nicht erfüllt wird. Die- `Take While` Klausel ist besonders nützlich, wenn Sie mit einem geordneten Abfrageergebnis arbeiten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die- `Take While` Klausel verwendet, um Ergebnisse abzurufen, bis der erste Kunde ohne Bestellungen gefunden wird.  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](index.md)
- [SELECT-Klausel](select-clause.md)
- [From-Klausel](from-clause.md)
- [Take-Klausel](take-clause.md)
- [SkipWhile-Klausel](skip-while-clause.md)
- [WHERE-Klausel](where-clause.md)
