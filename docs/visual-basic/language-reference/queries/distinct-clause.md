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
ms.openlocfilehash: 49eaab2e6a8c48d61518ea51ef2f644b6eb48314
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875282"
---
# <a name="distinct-clause-visual-basic"></a>Distinct-Klausel (Visual Basic)

Schränkt die Werte der aktuellen Bereichs Variablen ein, um doppelte Werte in nachfolgenden Abfrage Klauseln auszuschließen.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a>Bemerkungen  

 Mit der-Klausel können Sie `Distinct` eine Liste eindeutiger Elemente zurückgeben. Die- `Distinct` Klausel bewirkt, dass die Abfrage doppelte Abfrageergebnisse ignoriert. Die- `Distinct` Klausel gilt für doppelte Werte für alle Rückgabe Felder, die durch die-Klausel angegeben werden `Select` . Wenn keine- `Select` Klausel angegeben wird, `Distinct` wird die-Klausel auf die Bereichs Variable für die in der-Klausel identifizierte Abfrage angewendet `From` . Wenn es sich bei der Bereichs Variablen nicht um einen unveränderlichen Typ handelt, wird von der Abfrage nur ein Abfrageergebnis ignoriert, wenn alle Member des Typs mit einem vorhandenen Abfrageergebnis zu vergleichen sind.  
  
## <a name="example"></a>Beispiel  

 Der folgende Abfrage Ausdruck verbindet eine Liste von Kunden und eine Liste mit Kundenaufträgen. Die `Distinct` -Klausel ist enthalten, um eine Liste der eindeutigen Kundennamen und Bestelldaten zurückzugeben.  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](index.md)
- [From-Klausel](from-clause.md)
- [SELECT-Klausel](select-clause.md)
- [WHERE-Klausel](where-clause.md)
