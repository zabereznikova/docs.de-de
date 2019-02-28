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
ms.openlocfilehash: 545eefc67d52428470c19b62085fd87927505c7e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972702"
---
# <a name="let-clause-visual-basic"></a>Let-Klausel (Visual Basic)
Berechnet einen Wert aus, und weist es eine neue Variable in der Abfrage.  
  
## <a name="syntax"></a>Syntax  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`variable`|Erforderlich. Ein Alias, der verwendet werden kann, um die Ergebnisse des angegebenen Ausdrucks zu verweisen.|  
|`expression`|Erforderlich. Ein Ausdruck, der ausgewertet und der angegebenen Variablen zugewiesen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Let` -Klausel können Sie Werte für die einzelnen Abfrageergebnis, und verweisen sie mithilfe eines Alias zu berechnen. Der Alias kann verwendet werden in anderen Klauseln, z. B. die `Where` Klausel. Die `Let` -Klausel können Sie eine abfrageanweisung zu erstellen, ist einfacher zu lesen, da Sie geben Sie einen Alias für eine Expression-Klausel in der Abfrage enthalten, und ersetzen den Alias jedes Mal, die die Ausdrucksklausel verwendet wird, können.  
  
 Sie können eine beliebige Anzahl von einschließen `variable` und `expression` Zuweisungen in der `Let` Klausel. Trennen Sie jede Zuweisung durch ein Komma (,) ein.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die `Let` -Klausel, um einen Rabatt von 10 Prozent zu Produkten zu berechnen.  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a>Siehe auch
- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
