---
title: Abrufen von Objekten aus dem Identitätscache
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96c13903-ccb6-4a0e-ab6a-8ca955ca314d
ms.openlocfilehash: 457e11ddad16ca3be55f53f03c480b0e464ab38f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200393"
---
# <a name="retrieving-objects-from-the-identity-cache"></a>Abrufen von Objekten aus dem Identitätscache

In diesem Thema werden die Typen von LINQ to SQL-Abfragen beschrieben, die Objekte aus dem Identitäts-Cache abrufen, der vom <xref:System.Data.Linq.DataContext> verwaltet wird.  
  
 In LINQ to SQL besteht eine der Methoden zur <xref:System.Data.Linq.DataContext>-Objektverwaltung darin, Objektidentitäten in einem Identitäts-Cache zu protokollieren, während Abfragen ausgeführt werden. In einigen Fällen versucht LINQ to SQL, vor dem Ausführen einer Datenbankabfrage ein Objekt aus dem Identitäts-Cache abzurufen.  
  
 Damit eine LINQ to SQL-Abfrage ein Objekt aus dem Identitäts-Cache zurückgibt, muss die Abfrage im Regelfall auf dem Primärschlüssel eines Objekts basieren und ein einzelnes Objekt zurückgeben. Die Abfrage muss eine der im Folgenden gezeigten allgemeinen Formen aufweisen.  
  
> [!NOTE]
> Vorkompilierte Abfrage geben keine Objekte aus dem Identitäts-Cache zurück. Weitere Informationen zu vorkompilierten Abfragen finden Sie unter <xref:System.Data.Linq.CompiledQuery> und Gewusst [wie: Speichern und wieder verwenden von Abfragen](how-to-store-and-reuse-queries.md).  
  
 Eine Abfrage muss eine der folgenden allgemeinen Formen aufweisen, um ein Objekt aus dem Identitäts-Cache abzurufen:  
  
- <xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`  
  
- <xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`  
  
 In diesen allgemeinen Formen werden `Function1`, `Function2` und `predicate` wie folgt definiert.  
  
 `Function1` kann eine der folgenden Formen haben:  
  
- <xref:System.Linq.Queryable.Where%2A>  
  
- <xref:System.Linq.Queryable.First%2A>  
  
- <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
- <xref:System.Linq.Queryable.Single%2A>  
  
- <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 `Function2` kann eine der folgenden Formen haben:  
  
- <xref:System.Linq.Queryable.First%2A>  
  
- <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
- <xref:System.Linq.Queryable.Single%2A>  
  
- <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 `predicate` muss ein Ausdruck sein, in dem die Primärschlüsseleigenschaft des Objekts auf einen konstanten Wert festgelegt ist. Wenn der Primärschlüssel eines Objekts von mehreren Eigenschaften definiert wird, muss jede dieser Eigenschaften auf einen konstanten Wert festgelegt sein. Hier einige Beispiele der Form, die `predicate` aufweisen muss:  
  
- `c => c.PK == constant_value`  
  
- `c => c.PK1 == constant_value1 && c=> c.PK2 == constant_value2`  
  
## <a name="example"></a>Beispiel  

 Der folgende Code stellt Beispiele für die Typen von LINQ to SQL-Abfragen dar, die ein Objekt aus dem Identitäts-Cache abrufen.  
  
 [!code-csharp[L2S_QueryCache#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/l2s_querycache/cs/program.cs#1)]
 [!code-vb[L2S_QueryCache#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/l2s_querycache/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Abfragekonzepte](query-concepts.md)
- [Objektidentität](object-identity.md)
- [Hintergrundinformationen](background-information.md)
- [Objektidentität](object-identity.md)
