---
title: Skip While-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 47703e445865435f5bf5312c3fe41833ac21aa3f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333147"
---
# <a name="skip-while-clause-visual-basic"></a>Skip While-Klausel (Visual Basic)
Überspringt Elemente in einer Auflistung, solange eine angegebene Bedingung `true` ist, und gibt anschließend die übrigen Elemente zurück.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`expression`|Erforderlich Ein Ausdruck, der eine Bedingung darstellt, für die Elemente getestet werden sollen. Der Ausdruck muss einen `Boolean` Wert oder eine funktionale Entsprechung zurückgeben, z. b. eine `Integer`, die als `Boolean`ausgewertet werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Skip While`-Klausel umgeht Elemente vom Anfang eines Abfrage Ergebnisses, bis die angegebene `expression` `false`zurückgibt. Nachdem `expression` `false`zurückgegeben hat, gibt die Abfrage alle verbleibenden Elemente zurück. Der `expression` wird für die restlichen Ergebnisse ignoriert.  
  
 Die `Skip While`-Klausel unterscheidet sich von der `Where`-Klausel darin, dass die `Where`-Klausel verwendet werden kann, um alle Elemente aus einer Abfrage auszuschließen, die eine bestimmte Bedingung nicht erfüllen. Die `Skip While`-Klausel schließt Elemente nur dann aus, wenn die Bedingung zum ersten Mal nicht erfüllt wird. Die `Skip While`-Klausel ist besonders nützlich, wenn Sie mit einem geordneten Abfrageergebnis arbeiten.  
  
 Sie können eine bestimmte Anzahl von Ergebnissen ab dem Anfang eines Abfrage Ergebnisses umgehen, indem Sie die `Skip`-Klausel verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die `Skip While`-Klausel verwendet, um die Ergebnisse zu umgehen, bis der erste Kunde aus der USA gefunden wurde.  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Skip-Klausel](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Take While-Klausel](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
