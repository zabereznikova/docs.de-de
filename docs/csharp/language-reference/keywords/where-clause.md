---
title: where-Klausel (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0324346ee5e214bf467fcb522ef781c91fa1b76f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="where-clause-c-reference"></a>where-Klausel (C#-Referenz)
Die `where`-Klausel wird in einem Abfrageausdruck verwendet, um anzugeben, welche Elemente aus der Datenquelle im Abfrageausdruck zurückgegeben werden. Sie wendet eine boolesche Bedingung (*Prädikat*) auf jedes Quellelement an, auf das durch die Bereichsvariable verwiesen wird, und gibt die Elemente zurück, bei denen die angegebene Bedingung wahr ist. Ein einzelner Abfrageausdruck enthält möglicherweise mehrere `where`-Klauseln, und eine einzelne Klausel kann mehrere Teilausdrücke des Prädikats enthalten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel filtert die `where`-Klausel alle Zahlen mit Ausnahme derjenigen heraus, die niedriger als fünf sind. Wenn Sie die `where`-Klausel entfernen, werden alle Zahlen aus der Datenquelle zurückgegeben. Der Ausdruck `num < 5` ist das Prädikat, das auf jedes Element angewendet wird.  
  
 [!code-csharp[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Innerhalb einer einzelnen `where`-Klausel können Sie so viele Prädikate wie nötig angeben, indem Sie die Operatoren [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) und [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) verwenden. Im folgenden Beispiel gibt die Abfrage zwei Prädikate an, um nur die geraden Zahlen auszuwählen, die niedriger als fünf sind.  
  
 [!code-csharp[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]  
  
## <a name="example"></a>Beispiel  
 Eine `where`-Klausel kann eine oder mehrere Methoden enthalten, die boolesche Werte zurückgeben. Im folgenden Beispiel verwendet die `where`-Klausel eine Methode, um zu bestimmen, ob der aktuelle Wert der Bereichsvariable gerade oder ungerade ist.  
  
 [!code-csharp[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]  
  
## <a name="remarks"></a>Hinweise  
 Die `where`-Klausel ist ein Filtermechanismus. Sie kann praktisch überall in einem Abfrageausdruck positioniert werden; sie kann allerdings nicht die erste oder letzte Klausel sein. Eine `where`-Klausel kann entweder vor oder nach der [group](../../../csharp/language-reference/keywords/group-clause.md)-Klausel angezeigt werden, abhängig davon, ob Sie die Quellelemente vor oder nach deren Gruppierung filtern müssen.  
  
 Wenn ein angegebenes Prädikat nicht für die Elemente in der Datenquelle gültig ist, tritt ein Kompilierzeitfehler auf. Dies ist ein Vorteil der von [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] bereitgestellten starken Typprüfung.  
  
 Zur Kompilierzeit wird das Schlüsselwort `where` in einen Aufruf der Standardabfrageoperator-Methode <xref:System.Linq.Enumerable.Where%2A> konvertiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Abfrageschlüsselwörter (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
 [from-Klausel](../../../csharp/language-reference/keywords/from-clause.md)  
 [select-Klausel](../../../csharp/language-reference/keywords/select-clause.md)  
 [Filtern von Daten](../../programming-guide/concepts/linq/filtering-data.md)  
 [LINQ-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [Erste Schritte mit LINQ in C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
