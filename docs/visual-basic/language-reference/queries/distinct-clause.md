---
title: Distinct-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 3761f6d6ba97e7f1a824b70b18a50dae820c7e51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710039"
---
# <a name="distinct-clause-visual-basic"></a>Distinct-Klausel (Visual Basic)
Schränkt die Werte des die aktuelle Bereichsvariable, doppelte Werte in nachfolgenden Abfrageklauseln zu beseitigen.  
  
## <a name="syntax"></a>Syntax  
  
```  
Distinct  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `Distinct` -Klausel, um eine Liste von eindeutigen Elementen zurückzugeben. Die `Distinct` -Klausel bewirkt, dass die Abfrage, um doppelte Abfrageergebnisse zu ignorieren. Die `Distinct` Klausel gilt für doppelte Werte für alle Felder, die anhand des Zurückgeben der `Select` Klausel. Wenn kein `Select` -Klausel angegeben ist, die `Distinct` -Klausel wird angewendet, auf die Bereichsvariable für die Abfrage, der `From` Klausel. Ist die Bereichsvariable kein unveränderlicher Typ, ignoriert die Abfrage nur ein Abfrageergebnis zu, wenn alle Elemente des Typs einer vorhandenen Ergebnis der Abfrage übereinstimmen.  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrageausdruck verknüpft eine Liste von Kunden und eine Liste mit kundenbestellungen. Die `Distinct` -Klausel zum Zurückgeben einer Liste der Namen der eindeutigen Kunden und Sortieren von Datumsangaben enthalten ist.  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
