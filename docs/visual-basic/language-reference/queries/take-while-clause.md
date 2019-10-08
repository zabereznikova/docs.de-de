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
ms.openlocfilehash: fe6ee470698504bc0434930cc9aa6de712e04254
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004673"
---
# <a name="take-while-clause-visual-basic"></a>Take While-Klausel (Visual Basic)
Gibt Elemente in einer Auflistung zurück, solange eine angegebene Bedingung `true` ist, und überspringt dann die übrigen Elemente.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`expression`|Erforderlich. Ein Ausdruck, der eine Bedingung darstellt, für die Elemente getestet werden sollen. Der Ausdruck muss einen `Boolean`-Wert oder ein funktionales Äquivalent zurückgeben, z. b. ein `Integer`, das als `Boolean` ausgewertet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Take While`-Klausel enthält Elemente vom Anfang eines Abfrage Ergebnisses, bis der angegebene `expression` `false` zurückgibt. Nachdem der `expression` `false` zurückgegeben hat, umgeht die Abfrage alle verbleibenden Elemente. Der `expression` wird für die restlichen Ergebnisse ignoriert.  
  
 Die `Take While`-Klausel unterscheidet sich von der `Where`-Klausel darin, dass die `Where`-Klausel verwendet werden kann, um alle Elemente aus einer Abfrage aufzunehmen, die eine bestimmte Bedingung erfüllen. Die `Take While`-Klausel enthält Elemente nur bis zum ersten Mal, wenn die Bedingung nicht erfüllt wird. Die `Take While`-Klausel ist besonders nützlich, wenn Sie mit einem geordneten Abfrageergebnis arbeiten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die `Take While`-Klausel verwendet, um Ergebnisse abzurufen, bis der erste Kunde ohne Bestellungen gefunden wird.  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Take-Klausel](../../../visual-basic/language-reference/queries/take-clause.md)
- [Skip While-Klausel](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
