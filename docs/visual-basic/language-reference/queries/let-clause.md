---
title: Let-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 6484da5329c8240735b7c35f506637dd01cbeda4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="let-clause-visual-basic"></a>Let-Klausel (Visual Basic)
Berechnet einen Wert ein, und weist sie einer neuen Variablen innerhalb der Abfrage.  
  
## <a name="syntax"></a>Syntax  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`variable`|Erforderlich. Ein Alias, der verwendet werden kann, um auf die Ergebnisse des angegebenen Ausdrucks zu verweisen.|  
|`expression`|Erforderlich. Ein Ausdruck, der ausgewertet wird, und der angegebenen Variablen zugewiesen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Let` -Klausel ermöglicht es Ihnen, berechnen Sie Werte für die einzelnen Abfrageergebnis und über einen Alias zu verweisen. Der Alias kann z. B. in anderen Klauseln verwendet werden die `Where` Klausel. Die `Let` -Klausel ermöglichen es Ihnen, eine abfrageanweisung zu erstellen, ist einfacher zu lesen, da Geben Sie einen Alias für einen Ausdrucksklausel in der Abfrage enthaltenen und ersetzen den Alias jedes Mal wird die Ausdrucksklausel verwendet werden können.  
  
 Sie können eine beliebige Anzahl von einschließen `variable` und `expression` Zuweisungen in der `Let` Klausel. Trennen Sie jede Zuweisung durch ein Komma (,) ein.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird mit der `Let` -Klausel, um 10 Prozent Rabatt zu Produkten zu berechnen.  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Abfragen](../../../visual-basic/language-reference/queries/queries.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
