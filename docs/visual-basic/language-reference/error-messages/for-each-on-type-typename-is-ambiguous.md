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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 783c741a8acb0d27ef6ff5c52939bd12a026ba74
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a><span data-ttu-id="8bc76-102">"For Each" für Typ '&lt;Typename&gt;' ist mehrdeutig, da der Typ mehrere Instanziierungen von "System.Collections.Generic.IEnumerable (Of T)" implementiert.</span><span class="sxs-lookup"><span data-stu-id="8bc76-102">&#39;For Each&#39; on type &#39;&lt;typename&gt;&#39; is ambiguous because the type implements multiple instantiations of &#39;System.Collections.Generic.IEnumerable(Of T)&#39;</span></span>
<span data-ttu-id="8bc76-103">Ein `For Each` -Anweisung wird eine Iteratorvariable angegeben, die mehr als ein <xref:System.Collections.IEnumerable.GetEnumerator%2A>-Methode.</xref:System.Collections.IEnumerable.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="8bc76-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="8bc76-104">Iteratorvariablen, muss ein Typ, implementiert der <xref:System.Collections.IEnumerable?displayProperty=fullName>oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>Schnittstelle in einer der der `Collections` Namespaces und die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> </xref:System.Collections.IEnumerable?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8bc76-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=fullName> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> interface in one of the `Collections` namespaces of the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="8bc76-105">Es ist möglich, dass eine Klasse mehr als eine konstruierte generische Schnittstelle ein anderes Typargument für jede erstellte implementieren.</span><span class="sxs-lookup"><span data-stu-id="8bc76-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="8bc76-106">Wenn eine Klasse, dies hat, für die Iteratorvariable verwendet wird, wird diese Variable hat mehr als ein <xref:System.Collections.IEnumerable.GetEnumerator%2A>-Methode.</xref:System.Collections.IEnumerable.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="8bc76-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="8bc76-107">In diesem Fall [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] können nicht auswählen, welche Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8bc76-107">In such a case, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="8bc76-108">**Fehler-ID:** BC32096</span><span class="sxs-lookup"><span data-stu-id="8bc76-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8bc76-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8bc76-109">To correct this error</span></span>  
  
-   <span data-ttu-id="8bc76-110">Verwenden Sie [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) oder [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) , wandeln Sie den Typ der Iteratorvariablen an der Schnittstelle definieren die <xref:System.Collections.IEnumerable.GetEnumerator%2A>Methode, die Sie verwenden möchten.</xref:System.Collections.IEnumerable.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="8bc76-110">Use [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bc76-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bc76-111">See Also</span></span>  
 <span data-ttu-id="8bc76-112">[Für jede... Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8bc76-112">[For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span></span>  
<span data-ttu-id="8bc76-113"> [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)</span><span class="sxs-lookup"><span data-stu-id="8bc76-113"> [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)</span></span>
