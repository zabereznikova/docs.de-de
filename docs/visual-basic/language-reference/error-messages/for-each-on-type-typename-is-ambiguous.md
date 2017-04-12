---
title: "&quot;For Each&quot; für Typ &quot;&lt;Typename&gt;&quot; ist mehrdeutig, da der Typ mehrere Instanziierungen von &quot;System.Collections.Generic.IEnumerable (Of T)&quot; implementiert | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32096
- bc32096
dev_langs:
- VB
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6177b48cdc3bc4085cecb6d73c164684ef1c0bc6
ms.lasthandoff: 03/13/2017

---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a>"For Each" für Typ '&lt;Typename&gt;' ist mehrdeutig, da der Typ mehrere Instanziierungen von "System.Collections.Generic.IEnumerable (Of T)" implementiert.
Ein `For Each` -Anweisung wird eine Iteratorvariable angegeben, die mehr als ein <xref:System.Collections.IEnumerable.GetEnumerator%2A>-Methode.</xref:System.Collections.IEnumerable.GetEnumerator%2A>  
  
 Iteratorvariablen, muss ein Typ, implementiert der <xref:System.Collections.IEnumerable?displayProperty=fullName>oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>Schnittstelle in einer der der `Collections` Namespaces und die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> </xref:System.Collections.IEnumerable?displayProperty=fullName> Es ist möglich, dass eine Klasse mehr als eine konstruierte generische Schnittstelle ein anderes Typargument für jede erstellte implementieren. Wenn eine Klasse, dies hat, für die Iteratorvariable verwendet wird, wird diese Variable hat mehr als ein <xref:System.Collections.IEnumerable.GetEnumerator%2A>-Methode.</xref:System.Collections.IEnumerable.GetEnumerator%2A> In diesem Fall [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] können nicht auswählen, welche Methode aufgerufen.  
  
 **Fehler-ID:** BC32096  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden Sie [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) oder [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) , wandeln Sie den Typ der Iteratorvariablen an der Schnittstelle definieren die <xref:System.Collections.IEnumerable.GetEnumerator%2A>Methode, die Sie verwenden möchten.</xref:System.Collections.IEnumerable.GetEnumerator%2A>  
  
## <a name="see-also"></a>Siehe auch  
 [Für jede... Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
