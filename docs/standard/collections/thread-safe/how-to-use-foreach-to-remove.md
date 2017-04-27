---
title: 'Gewusst wie: Entfernen von Elementen in einer BlockingCollection mit ForEach | Microsoft-Dokumentation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collectoin
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 88d36d440b6a1d79f978e2cf39bbe2cde241af6b
ms.lasthandoff: 04/18/2017

---
# <a name="how-to-use-foreach-to-remove-items-in-a-blockingcollection"></a>Gewusst wie: Entfernen von Elementen in einer BlockingCollection mit ForEach
Über die Entnahme von Elementen aus einer <xref:System.Collections.Concurrent.BlockingCollection%601> mithilfe der Methoden <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> und <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> hinaus können Sie außerdem [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md) ([For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) in Visual Basic) zum Entfernen von Elementen verwenden, bis das Hinzufügen abgeschlossen und die Sammlung leer ist. Dies wird als *mutierende Enumeration* oder *verbrauchende Enumeration* bezeichnet, da dieser Enumerator, im Gegensatz zu einer typischen `foreach`- (`For Each`-)Schleife, die Quellsammlung durch Entfernen von Elementen verändert.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie alle Elemente in einer <xref:System.Collections.Concurrent.BlockingCollection%601> mithilfe einer `foreach`- (`For Each`-)Schleife entfernt werden.  
  
 [!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
 [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]  
  
 In diesem Beispiel wird eine `foreach`-Schleife mit der <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName>-Methode im verbrauchenden Thread verwendet, was die Entfernung jedes Elements aus der Sammlung bei dessen Aufzählung bewirkt. <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> begrenzt die maximale Anzahl von Elementen, die sich zu einem bestimmten Zeitpunkt in der Auflistung befinden können. Durch Aufzählen der Auflistung auf diese Weise wird der Consumerthread blockiert, wenn keine Elemente verfügbar sind oder die Auflistung leer ist. In diesem Beispiel ist eine Blockierung kein Problem, da der Producerthread Elemente schneller hinzufügt als sie verbraucht werden können.  
  
 Es gibt keine Garantie dafür, dass die Elemente in der gleichen Reihenfolge aufgezählt werden, in der sie von den Producerthreads hinzugefügt werden.  
  
 Um die Sammlung aufzuzählen, ohne sie zu ändern, verwenden Sie einfach `foreach` (`For Each`) ohne die Methode <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>. Es ist jedoch wichtig zu wissen, dass diese Art der Enumeration eine Momentaufnahme der Auflistung zu einem genauen Zeitpunkt darstellt. Wenn weitere Threads gleichzeitig Elemente hinzufügen oder entfernen, während die Schleife ausgeführt wird, stellt die Schleife möglicherweise nicht den tatsächlichen Zustand der Auflistung dar.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Parallele Programmierung](../../../../docs/standard/parallel-programming/index.md)
