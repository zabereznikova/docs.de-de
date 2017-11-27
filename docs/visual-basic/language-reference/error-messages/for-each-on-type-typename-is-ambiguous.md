---
title: "&#39; Für jede &#39; auf Typ &#39; &lt;Typename&gt;&#39; ist mehrdeutig, da der Typ mehrere Instanziierungen von &#39; implementiert. System.Collections.Generic.IEnumerable (Of T) &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords: BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a74178f3f0b2e7589b87046973473582993f3ed9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a>&#39; Für jede &#39; auf Typ &#39; &lt;Typename&gt;&#39; ist mehrdeutig, da der Typ mehrere Instanziierungen von &#39; implementiert. System.Collections.Generic.IEnumerable (Of T) &#39;
Ein `For Each` -Anweisung gibt eine Iteratorvariable, die weist mehr als eine <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode.  
  
 Die Iteratorvariable muss ein Typ, implementiert der <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> Schnittstelle in einer der der `Collections` Namespaces und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Es ist möglich, dass eine Klasse, um ein anderes Typargument für jeden Konstruktion mit mehr als eine konstruierte generische-Schnittstelle implementieren. Wenn eine Klasse, die dies tut, für die Iteratorvariable verwendet wird, wird diese Variable hat mehr als ein <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode. In einem solchen Fall [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] können nicht auswählen, welche Methode aufgerufen.  
  
 **Fehler-ID:** BC32096  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden Sie [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) oder [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) umwandeln den Iterator Variablentyp auf die Schnittstelle zum Definieren der <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode, die Sie verwenden möchten.  
  
## <a name="see-also"></a>Siehe auch  
 [For Each...Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
