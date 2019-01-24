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
ms.openlocfilehash: de7ef8aa456235b4fd3003230645db4f5a813a9c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634063"
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
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
