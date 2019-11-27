---
title: Distinct-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 94471898807ef4552564c3e01465f2b2f6211d0c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335381"
---
# <a name="distinct-clause-visual-basic"></a>Distinct-Klausel (Visual Basic)
Schränkt die Werte der aktuellen Bereichs Variablen ein, um doppelte Werte in nachfolgenden Abfrage Klauseln auszuschließen.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a>Hinweise  
 Mit der `Distinct`-Klausel können Sie eine Liste eindeutiger Elemente zurückgeben. Die `Distinct`-Klausel bewirkt, dass die Abfrage doppelte Abfrageergebnisse ignoriert. Die `Distinct`-Klausel gilt für doppelte Werte für alle Rückgabe Felder, die durch die `Select`-Klausel angegeben werden. Wenn keine `Select`-Klausel angegeben wird, wird die `Distinct`-Klausel auf die Bereichs Variable der in der `From`-Klausel identifizierten Abfrage angewendet. Wenn es sich bei der Bereichs Variablen nicht um einen unveränderlichen Typ handelt, wird von der Abfrage nur ein Abfrageergebnis ignoriert, wenn alle Member des Typs mit einem vorhandenen Abfrageergebnis zu vergleichen sind.  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrage Ausdruck verbindet eine Liste von Kunden und eine Liste mit Kundenaufträgen. Die `Distinct`-Klausel ist enthalten, um eine Liste der eindeutigen Kundennamen und Bestelldaten zurückzugeben.  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
