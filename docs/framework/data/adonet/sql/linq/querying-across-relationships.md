---
title: Beziehungsübergreifendes Abfragen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 297878d0-685b-4c01-b2e0-9d731b7322bc
ms.openlocfilehash: 24ab13a1d67eac39c7b3d7be8cb1c16ec7265d5e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184880"
---
# <a name="querying-across-relationships"></a>Beziehungsübergreifendes Abfragen

Verweise auf andere Objekte oder Auflistungen in Ihren Klassendefinitionen entsprechen direkt den Fremdschlüsselbeziehungen in der Datenbank. Sie können diese Beziehungen nutzen, wenn Sie eine Abfrage mit der dot-Schreibweise vornehmen, um auf die Beziehungseigenschaften zuzugreifen und von einem Objekt zu einem anderen zu navigieren. Diese Zugriffsoperationen werden in komplexere Joins oder korrelierte Unterabfragen in den entsprechenden SQL-Befehlen übersetzt.  
  
 Die folgende Abfrage navigiert beispielsweise von Bestellungen zu Kunden und bietet somit die Möglichkeit, die Ergebnisse auf Bestellungen von Kunden aus London einzugrenzen.  
  
 [!code-csharp[DLinqQueryConcepts#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#3)]
 [!code-vb[DLinqQueryConcepts#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#3)]  
  
 Wenn keine Beziehungs Eigenschaften vorhanden waren, müssten Sie Sie manuell als *Joins*schreiben, genauso wie in einer SQL-Abfrage, wie im folgenden Code:  
  
 [!code-csharp[DLinqQueryConcepts#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#4)]
 [!code-vb[DLinqQueryConcepts#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#4)]  
  
 Sie können die *Beziehungs* Eigenschaft verwenden, um diese Beziehung einmal zu definieren. Sie können dann die zweckmäßigere dot-Syntax verwenden. Beziehungseigenschaften sind jedoch vor allem vorhanden, da fachspezifische Objektmodelle i. d. R. als Hierarchien oder Graphen definiert werden. Die Objekte, für die Sie programmieren, verfügen über Verweise auf andere Objekte. Es ist lediglich ein glücklicher Zufall, dass Objekt-zu-Objekt-Beziehungen fremdschlüsselformatierten Beziehungen in Datenbanken entsprechen. Der Eigenschaftenzugriff bietet eine zweckmäßige Möglichkeit, Joins zu schreiben.  
  
 Unter diesem Aspekt sind Beziehungseigenschaften auf der Ergebnisseite einer Abfrage wichtiger als auf der Seite der Abfrage selbst. Nachdem die Abfrage Daten zu einem bestimmten Kunden abgerufen hat, gibt die Klassendefinition an, dass der Kunde Bestellungen aufweist. Mit anderen Worten: Sie gehen davon aus, dass die `Orders`-Eigenschaft eines bestimmten Kunden eine Auflistung ist, die alle Bestellungen dieses Kunden enthält. Das ist in der Tat der Vertrag, den Sie durch Definition der Klassen auf diese Weise deklariert haben. Sie erwarten, die Bestellungen zu sehen, auch wenn die Abfrage keine Bestellungen abgerufen hat. Sie gehen davon aus, dass Ihr Objektmodell die Illusion erhält, dass es sich um eine im Arbeitsspeicher befindliche Erweiterung der Datenbank handelt, bei der die verwandten Objekte sofort verfügbar sind.  
  
 Da Sie nun über Beziehungen verfügen, können Sie Abfragen schreiben, die auf die in Ihren Klassen definierten Beziehungseigenschaften Bezug nehmen. Diese Beziehungsverweise entsprechen Fremdschlüsselbeziehungen in der Datenbank. Operationen, die diese Beziehungen verwenden, werden in komplexere Joins in der entsprechenden SQL übersetzt. Sofern Sie (mit dem <xref:System.Data.Linq.Mapping.AssociationAttribute>-Attribut) eine Beziehung definiert haben, müssen Sie in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] keinen expliziten Join codieren.  
  
 Um diese Illusion aufrechtzuerhalten, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implementiert eine Technik, die als *Verzögertes Laden*bezeichnet wird. Weitere Informationen finden Sie unter [Verzögertes im Vergleich zu unmittelbarem laden](deferred-versus-immediate-loading.md).  
  
 Beachten Sie die folgende SQL-Abfrage, um eine Liste von Paaren zu projizieren `CustomerID` - `OrderID` :  
  
```sql
SELECT t0.CustomerID, t1.OrderID  
FROM   Customers AS t0 INNER JOIN  
          Orders AS t1 ON t0.CustomerID = t1.CustomerID  
WHERE  (t0.City = @p0)  
```  
  
 Wenn Sie mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die gleichen Ergebnisse erzielen möchten, verwenden Sie den `Orders`-Eigenschaftenverweis, der bereits in der `Customer`-Klasse existiert. Der `Orders` Verweis enthält die erforderlichen Informationen zum Ausführen der Abfrage und zum Projizieren der `CustomerID` - `OrderID` Paare, wie im folgenden Code:  
  
 [!code-csharp[DLinqQueryConcepts#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#5)]
 [!code-vb[DLinqQueryConcepts#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#5)]  
  
 Sie können auch umgekehrt vorgehen. In diesem Fall fragen Sie `Orders` (Bestellungen) ab und verwenden den `Customer`-Beziehungsverweis für den Zugriff auf Informationen zum zugehörigen `Customer`-Objekt. Der folgende Code projiziert die gleichen `CustomerID` - `OrderID` Paare wie zuvor, aber dieses Mal durch Abfragen `Orders` anstelle von `Customers` .  
  
 [!code-csharp[DLinqQueryConcepts#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#6)]
 [!code-vb[DLinqQueryConcepts#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#6)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Abfragekonzepte](query-concepts.md)
