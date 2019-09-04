---
title: Ausdrücke in LINQ to Entities-Abfragen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: 5262d2bca07525aba6db5303e730c8b358641d52
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250975"
---
# <a name="expressions-in-linq-to-entities-queries"></a>Ausdrücke in LINQ to Entities-Abfragen
Ein Ausdruck ist ein Codefragment, das als einzelner Wert, einzelnes Objekt, einzelne Methode oder einzelner Namespace ausgewertet werden kann. Ausdrücke können einen literalen Wert, einen Methodenaufruf, einen Operator und die entsprechenden Operanden oder einen einfachen Namen enthalten. Einfache Namen können der Name einer Variablen, eines Typmembers, eines Methodenparameters, eines Namespaces oder eines Typs sein. Ausdrücke können Operatoren verwenden, die wiederum andere Ausdrücke als Parameter oder Methodenaufrufe verwenden können, deren Parameter wiederum andere Methodenaufrufe darstellen. Die Bandbreite der möglichen Ausdrücke reicht daher von einfach bis sehr komplex.  
  
 In LINQ to Entities-Abfragen können Ausdrücke beliebige Elemente enthalten, die von den Typen <xref:System.Linq.Expressions> im-Namespace zugelassen werden, einschließlich Lambda-Ausdrücken. Die Ausdrücke, die in LINQ to Entities Abfragen verwendet werden können, sind eine übergeordnete Menge der Ausdrücke, die zum Abfragen [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]von verwendet werden können.  Ausdrücke, die Teil von Abfragen [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] für sind, sind auf Vorgänge beschränkt, die von `ObjectQuery<T>` und der zugrunde liegenden Datenquelle unterstützt werden.  
  
 Im folgenden Beispiel ist der Vergleich in der `Where`-Klausel ein Ausdruck:  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
> Bestimmte Sprachkonstrukte, wie C# `unchecked`z. b., haben keine Bedeutung in LINQ to Entities.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Constant Expressions (Konstante Ausdrücke)](constant-expressions.md)  
  
 [Vergleichsausdrücke](comparison-expressions.md)  
  
 [NULL-Vergleiche](null-comparisons.md)  
  
 [Initialisierungsausdrücke](initialization-expressions.md)  
  
 [Beziehungen, Navigations Eigenschaften und Fremdschlüssel](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET Entity Framework](../index.md)
