---
title: "Beziehungs&#252;bergreifende Abfragen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 297878d0-685b-4c01-b2e0-9d731b7322bc
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Beziehungs&#252;bergreifende Abfragen
Verweise auf andere Objekte oder Auflistungen in Ihren Klassendefinitionen entsprechen direkt den Fremdschlüsselbeziehungen in der Datenbank.  Sie können diese Beziehungen nutzen, wenn Sie eine Abfrage mit der dot\-Schreibweise vornehmen, um auf die Beziehungseigenschaften zuzugreifen und von einem Objekt zu einem anderen zu navigieren.  Diese Zugriffsoperationen werden in komplexere Joins oder korrelierte Unterabfragen in den entsprechenden SQL\-Befehlen übersetzt.  
  
 Die folgende Abfrage navigiert beispielsweise von Bestellungen zu Kunden und bietet somit die Möglichkeit, die Ergebnisse auf Bestellungen von Kunden aus London einzugrenzen.  
  
 [!code-csharp[DLinqQueryConcepts#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#3)]
 [!code-vb[DLinqQueryConcepts#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#3)]  
  
 Wenn keine Beziehungseigenschaften existieren, müssen Sie diese manuell als *Joins* schreiben, wie Sie es in einer SQL\-Abfrage tun würden. Siehe dazu den folgenden Code:  
  
 [!code-csharp[DLinqQueryConcepts#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#4)]
 [!code-vb[DLinqQueryConcepts#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#4)]  
  
 Sie können die Eigenschaft *Beziehung* verwenden, um diese besondere Beziehung einmalig zu definieren.  Sie können dann die zweckmäßigere dot\-Syntax verwenden.  Beziehungseigenschaften sind jedoch vor allem vorhanden, da fachspezifische Objektmodelle i. d. R. als Hierarchien oder Graphen definiert werden.  Die Objekte, für die Sie programmieren, verfügen über Verweise auf andere Objekte.  Es ist lediglich ein glücklicher Zufall, dass Objekt\-zu\-Objekt\-Beziehungen fremdschlüsselformatierten Beziehungen in Datenbanken entsprechen.  Der Eigenschaftenzugriff bietet eine zweckmäßige Möglichkeit, Joins zu schreiben.  
  
 Unter diesem Aspekt sind Beziehungseigenschaften auf der Ergebnisseite einer Abfrage wichtiger als auf der Seite der Abfrage selbst.  Nachdem die Abfrage Daten zu einem bestimmten Kunden abgerufen hat, gibt die Klassendefinition an, dass der Kunde Bestellungen aufweist.  Mit anderen Worten: Sie gehen davon aus, dass die `Orders`\-Eigenschaft eines bestimmten Kunden eine Auflistung ist, die alle Bestellungen dieses Kunden enthält.  Das ist in der Tat der Vertrag, den Sie durch Definition der Klassen auf diese Weise deklariert haben.  Sie erwarten, die Bestellungen zu sehen, auch wenn die Abfrage keine Bestellungen abgerufen hat.  Sie gehen davon aus, dass Ihr Objektmodell die Illusion erhält, dass es sich um eine im Arbeitsspeicher befindliche Erweiterung der Datenbank handelt, bei der die verwandten Objekte sofort verfügbar sind.  
  
 Da Sie nun über Beziehungen verfügen, können Sie Abfragen schreiben, die auf die in Ihren Klassen definierten Beziehungseigenschaften Bezug nehmen.  Diese Beziehungsverweise entsprechen Fremdschlüsselbeziehungen in der Datenbank.  Operationen, die diese Beziehungen verwenden, werden in komplexere Joins in der entsprechenden SQL übersetzt.  Sofern Sie \(mit dem <xref:System.Data.Linq.Mapping.AssociationAttribute>\-Attribut\) eine Beziehung definiert haben, müssen Sie in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] keinen expliziten Join codieren.  
  
 Um Sie dabei zu unterstützen, diese Illusion aufrechtzuerhalten, implementiert [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] eine Technik mit dem Namen *verzögertes Laden.* Weitere Informationen finden Sie unter [Verzögertes und unmittelbares Laden](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
 Verwenden Sie die folgende SQL\-Abfrage, um eine Liste von `CustomerID`\-`OrderID`\-Paaren zu projizieren:  
  
```  
SELECT t0.CustomerID, t1.OrderID  
FROM   Customers AS t0 INNER JOIN  
          Orders AS t1 ON t0.CustomerID = t1.CustomerID  
WHERE  (t0.City = @p0)  
```  
  
 Wenn Sie mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die gleichen Ergebnisse erzielen möchten, verwenden Sie den `Orders`\-Eigenschaftenverweis, der bereits in der `Customer`\-Klasse existiert.  Der `Orders`\-Verweis bietet die erforderlichen Informationen zum Ausführen der Abfrage und zum Projizieren der `CustomerID`\-`OrderID`\-Paare. Siehe hierzu den folgenden Code:  
  
 [!code-csharp[DLinqQueryConcepts#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#5)]
 [!code-vb[DLinqQueryConcepts#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#5)]  
  
 Sie können auch umgekehrt vorgehen.  In diesem Fall fragen Sie `Orders` \(Bestellungen\) ab und verwenden den `Customer`\-Beziehungsverweis für den Zugriff auf Informationen zum zugehörigen `Customer`\-Objekt.  Der folgende Code projiziert die gleichen `CustomerID`\-`OrderID`\-Paare wie zuvor. In diesem Fall werden jedoch `Orders` anstelle von `Customers` abgefragt.  
  
 [!code-csharp[DLinqQueryConcepts#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#6)]
 [!code-vb[DLinqQueryConcepts#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#6)]  
  
## Siehe auch  
 [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)