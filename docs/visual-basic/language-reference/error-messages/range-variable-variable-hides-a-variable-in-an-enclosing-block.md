---
title: "Bereichsvariablen &lt;Variable&gt; verbirgt eine Variable in einem einschließenden Block, eine zuvor definierte Bereichsvariable oder eine implizit deklarierte Variable in einem Abfrageausdruck"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ccbac48694a13daa09f2511cf39d5dbd51cdaaf7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="range-variable-ltvariablegt-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a>Bereichsvariablen &lt;Variable&gt; verbirgt eine Variable in einem einschließenden Block, eine zuvor definierte Bereichsvariable oder eine implizit deklarierte Variable in einem Abfrageausdruck
Ein im angegebenen Bereich-Variablenname eine `Select`, `From`, `Aggregate`, oder `Let` Klausel, um Duplikate der Name einer Bereichsvariablen, die bereits zuvor in der Abfrage oder den Namen einer Variablen, die von der Abfrage wird implizit deklariert wird angegeben z. B. ein Feldname oder der Name einer Aggregatfunktion.  
  
 **Fehler-ID:** BC36633  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass alle Bereichsvariablen in einem bestimmten Abfragebereich eindeutige Namen aufweisen. Sie können eine Abfrage einschließen, in Klammern einschließen, um sicherzustellen, dass geschachtelte Abfragen einen eindeutigen Bereich verfügen.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Let-Klausel](../../../visual-basic/language-reference/queries/let-clause.md)  
 [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
