---
title: Ausdrücke in LINQ to Entities-Abfragen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: 0b77fc4c2a7c7df6efc9f4d8ce4001c39250ab94
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539901"
---
# <a name="expressions-in-linq-to-entities-queries"></a>Ausdrücke in LINQ to Entities-Abfragen
Ein Ausdruck ist ein Codefragment, das als einzelner Wert, einzelnes Objekt, einzelne Methode oder einzelner Namespace ausgewertet werden kann. Ausdrücke können einen literalen Wert, einen Methodenaufruf, einen Operator und die entsprechenden Operanden oder einen einfachen Namen enthalten. Einfache Namen können der Name einer Variablen, eines Typmembers, eines Methodenparameters, eines Namespaces oder eines Typs sein. Ausdrücke können Operatoren verwenden, die wiederum andere Ausdrücke als Parameter oder Methodenaufrufe verwenden können, deren Parameter wiederum andere Methodenaufrufe darstellen. Die Bandbreite der möglichen Ausdrücke reicht daher von einfach bis sehr komplex.  
  
 In LINQ to Entities-Abfragen können Ausdrücke alles enthalten, zulässigen Typen innerhalb der <xref:System.Linq.Expressions> -Namespace, einschließlich der Lambda-Ausdrücke. Die Ausdrücke, die in LINQ to Entities-Abfragen verwendet werden können sind eine Obermenge der Ausdrücke, die verwendet werden können, die Abfrage die [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].  Ausdrücke, die Teil einer Abfrage der [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] sind von unterstützten Vorgänge auf `ObjectQuery<T>` und der zugrunde liegenden Datenquelle.  
  
 Im folgenden Beispiel ist der Vergleich in der `Where`-Klausel ein Ausdruck:  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  Bestimmte Sprachkonstrukte, z. B. C# `unchecked`, haben keine Bedeutung in LINQ to Entities.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Constant Expressions (Konstante Ausdrücke)](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [Vergleichsausdrücke](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [NULL-Vergleiche](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [Initialisierungsausdrücke](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [Beziehungen, Navigationseigenschaften und Fremdschlüssel](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)
