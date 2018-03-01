---
title: "Distinct-Klausel (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ed92d5d601c1ec329728346ac881c4fa2bad8aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="distinct-clause-visual-basic"></a>Distinct-Klausel (Visual Basic)
Schränkt die Werte der aktuellen Bereichsvariablen doppelte Werte in nachfolgenden Abfrageklauseln zu vermeiden.  
  
## <a name="syntax"></a>Syntax  
  
```  
Distinct  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `Distinct` -Klausel, um eine Liste von eindeutigen Elementen zurückzugeben. Die `Distinct` -Klausel bewirkt, dass die Abfrage, um doppelte Abfrageergebnisse zu ignorieren. Die `Distinct` -Klausel gilt für doppelte Werte für alle Felder, die vom angegebenen Zurückgeben der `Select` Klausel. Wenn kein `Select` -Klausel angegeben ist, die `Distinct` -Klausel wird angewendet, für die Bereichsvariable für die Abfrage identifiziert, der `From` Klausel. Ist die Bereichsvariable kein unveränderlicher Typ, ignoriert die Abfrage nur ein Abfrageergebnisses, wenn alle Elemente des Typs ein vorhandenes Abfrageergebnis übereinstimmen.  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrageausdruck verknüpft eine Liste von Kunden und eine Liste mit Kundenaufträgen. Die `Distinct` -Klausel zum Zurückgeben einer Liste von eindeutigen Kundennamen und Bestelldaten enthalten ist.  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Abfragen](../../../visual-basic/language-reference/queries/queries.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
