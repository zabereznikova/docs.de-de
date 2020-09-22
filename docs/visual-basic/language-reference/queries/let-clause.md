---
title: Let-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: a6ff3fc80a2b6752c61a8b8f7d4ce62b5a46baad
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869886"
---
# <a name="let-clause-visual-basic"></a>Let-Klausel (Visual Basic)

Berechnet einen Wert und weist ihn einer neuen Variablen in der Abfrage zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`variable`|Erforderlich. Ein Alias, der zum Verweisen auf die Ergebnisse des angegebenen Ausdrucks verwendet werden kann.|  
|`expression`|Erforderlich. Ein Ausdruck, der ausgewertet und der angegebenen Variablen zugewiesen wird.|  
  
## <a name="remarks"></a>Bemerkungen  

 Mit der `Let` -Klausel können Sie Werte für jedes Abfrageergebnis berechnen und mithilfe eines Alias referenzieren. Der Alias kann in anderen Klauseln verwendet werden, z. b. in der- `Where` Klausel. Mit der- `Let` Klausel können Sie eine Abfrage Anweisung erstellen, die leichter lesbar ist, da Sie einen Alias für eine in der Abfrage enthaltene Ausdrucks Klausel angeben und bei jeder Verwendung der Expression-Klausel den Alias ersetzen können.  
  
 Sie können eine beliebige Anzahl von `variable` -und- `expression` Zuweisungen in die- `Let` Klausel einschließen. Trennen Sie jede Zuweisung durch ein Komma (,).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Codebeispiel wird die- `Let` Klausel verwendet, um einen Rabatt von 10% auf Produkte zu berechnen.  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](index.md)
- [SELECT-Klausel](select-clause.md)
- [From-Klausel](from-clause.md)
- [WHERE-Klausel](where-clause.md)
