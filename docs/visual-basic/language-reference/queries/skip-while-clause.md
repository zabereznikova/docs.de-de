---
title: SkipWhile-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: b357320a92ace1b7a261991737ed653d54d0eeab
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359644"
---
# <a name="skip-while-clause-visual-basic"></a>Skip While-Klausel (Visual Basic)
Überspringt Elemente in einer Auflistung, solange eine angegebene Bedingung `true` ist, und gibt anschließend die übrigen Elemente zurück.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`expression`|Erforderlich. Ein Ausdruck, der eine Bedingung darstellt, für die Elemente getestet werden sollen. Der Ausdruck muss einen `Boolean` Wert oder eine funktionale Entsprechung zurückgeben, z. b. eine, die `Integer` als ausgewertet wird `Boolean` .|  
  
## <a name="remarks"></a>Bemerkungen  
 Die- `Skip While` Klausel umgeht Elemente vom Anfang eines Abfrage Ergebnisses, bis der angegebene `expression` zurückgibt `false` . Nachdem `expression` zurückgegeben `false` wurde, gibt die Abfrage alle verbleibenden Elemente zurück. Der `expression` wird für die restlichen Ergebnisse ignoriert.  
  
 Die- `Skip While` Klausel unterscheidet sich von der- `Where` Klausel darin, dass die- `Where` Klausel verwendet werden kann, um alle Elemente aus einer Abfrage auszuschließen, die eine bestimmte Bedingung nicht erfüllen. Die- `Skip While` Klausel schließt Elemente nur dann aus, wenn die Bedingung zum ersten Mal nicht erfüllt wird. Die- `Skip While` Klausel ist besonders nützlich, wenn Sie mit einem geordneten Abfrageergebnis arbeiten.  
  
 Sie können eine bestimmte Anzahl von Ergebnissen ab dem Anfang eines Abfrage Ergebnisses umgehen, indem Sie die- `Skip` Klausel verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die- `Skip While` Klausel verwendet, um die Ergebnisse zu umgehen, bis der erste Kunde aus der USA gefunden wurde.  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](index.md)
- [SELECT-Klausel](select-clause.md)
- [From-Klausel](from-clause.md)
- [Skip-Klausel](skip-clause.md)
- [TakeWhile-Klausel](take-while-clause.md)
- [WHERE-Klausel](where-clause.md)
