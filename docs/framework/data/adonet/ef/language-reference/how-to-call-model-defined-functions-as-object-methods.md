---
title: "Gewusst wie: Aufrufen von modelldefinierten Funktionen als Objektmethoden | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 33bae8a8-4ed8-4a1f-85d1-c62ff288cc61
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Gewusst wie: Aufrufen von modelldefinierten Funktionen als Objektmethoden
In diesem Thema wird beschrieben, wie eine modelldefinierte Funktion als Methode für ein <xref:System.Data.Objects.ObjectContext>\-Objekt oder als statische Methode für eine benutzerdefinierte Klasse aufgerufen wird.  Eine *modelldefinierte Funktion* ist eine Funktion, die im konzeptionellen Modell definiert wird.  Die folgenden Prozeduren beschreiben, wie diese Funktionen direkt aufgerufen werden, anstatt sie von LINQ to Entities\-Abfragen aufzurufen.  Informationen zum Aufrufen von modelldefinierten Funktionen in LINQ to Entities\-Abfragen finden Sie unter [Gewusst wie: Aufrufen von vom Modell definierten Funktionen in Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md).  
  
 Egal, ob Sie eine modelldefinierte Funktion als <xref:System.Data.Objects.ObjectContext>\-Methode oder statische Methode für eine benutzerdefinierte Klasse aufrufen: Zuerst muss die Methode der modelldefinierten Funktion mit einem <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> zugeordnet werden.  Wenn Sie jedoch für die <xref:System.Data.Objects.ObjectContext>\-Klasse eine Methode definieren, müssen Sie den LINQ\-Anbieter mithilfe der <xref:System.Data.Objects.ObjectContext.QueryProvider%2A>\-Eigenschaft bereitstellen. Wenn Sie jedoch für eine benutzerdefinierte Klasse eine statische Methode definieren, müssen Sie den LINQ\-Anbieter mithilfe der <xref:System.Linq.IQueryable.Provider%2A>\-Eigenschaft bereitstellen.  Weitere Informationen finden Sie in den Beispielen im Anschluss an die folgenden Prozeduren.  
  
 Die folgenden Prozeduren stellen in knapper Form dar, wie eine modelldefinierte Funktion als Methode für ein <xref:System.Data.Objects.ObjectContext>\-Objekt und als statische Methode für eine benutzerdefinierte Klasse aufgerufen wird.  Die folgenden Beispiele enthalten weitere Details zu den Schritten in den Prozeduren.  In den Prozeduren wird davon ausgegangen, dass eine Funktion im konzeptionellen Modell definiert wurde.  Weitere Informationen finden Sie unter [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/de-de/0dad7b8b-58f6-4271-b238-f34810d68e5f).  
  
### So rufen Sie eine modelldefinierte Funktion als Methode für ein ObjectContext\-Objekt auf  
  
1.  Fügen Sie eine Quelldatei hinzu, um die partielle von den Entity Framework\-Tools generierte und von der <xref:System.Data.Objects.ObjectContext> Klasse abgeleitete Klasse zu erweitern.  Durch die Definition des CLR\-Stub in einer separaten Quelldatei werden die Änderungen bei der erneuten Erstellung der Datei beibehalten.  
  
2.  Fügen Sie der <xref:System.Data.Objects.ObjectContext>\-Klasse, die wie folgt vorgeht, eine Common Language Runtime \(CLR\)\-Methode hinzu:  
  
    -   Sie ordnet der im konzeptionellen Modell definierten Funktion Objekte zu.  Zum Zuordnen der Methode müssen Sie ein <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> für die Methode übernehmen.  Beachten Sie, dass der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A>\-Parameter und der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A>\-Parameter des Attributs im konzeptionellen Modell den Namespacenamen und den Funktionsnamen darstellen.  Bei der Funktionsnamenauflösung für LINQ wird die Groß\-\/Kleinschreibung berücksichtigt.  
  
    -   Gibt die Ergebnisse der <xref:System.Linq.IQueryProvider.Execute%2A>\-Methode zurück, die von der <xref:System.Data.Objects.ObjectContext.QueryProvider%2A>\-Eigenschaft zurückgegeben werden.  
  
3.  Rufen Sie die statische Methode als ein Member für eine Instanz der <xref:System.Data.Objects.ObjectContext>\-Klasse auf.  
  
### So rufen Sie eine modelldefinierte Funktion als statische Methode für eine benutzerdefinierte Klasse auf  
  
1.  Fügen Sie der Anwendung eine Klasse mit einer statischen Methode hinzu, die wie folgt vorgeht:  
  
    -   Sie ordnet der im konzeptionellen Modell definierten Funktion Objekte zu.  Zum Zuordnen der Methode müssen Sie ein <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> für die Methode übernehmen.  Beachten Sie, dass der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A>\-Parameter und der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A>\-Parameter des Attributs im konzeptionellen Modell den Namespacenamen und den Funktionsnamen darstellen.  
  
    -   Akzeptiert ein <xref:System.Linq.IQueryable>\-Argument.  
  
    -   Gibt die Ergebnisse der <xref:System.Linq.IQueryProvider.Execute%2A>\-Methode zurück, die von der <xref:System.Linq.IQueryable.Provider%2A>\-Eigenschaft zurückgegeben werden.  
  
2.  Aufrufen der Methode als Member einer statischen Methode für die benutzerdefinierte Klasse  
  
## Beispiel  
 **Aufrufen einer modelldefinierten Funktion als Methode für ein ObjectContext\-Objekt**  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine modelldefinierte Funktion als Methode für ein <xref:System.Data.Objects.ObjectContext>\-Objekt aufgerufen wird.  Im Beispiel wird das [AdventureWorks Sales\-Modell](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832) verwendet.  
  
 Erwägen Sie die Verwendung der folgenden konzeptionellen Modellfunktion, die Produkteinnahmen für ein angegebenes Produkt zurückgibt.  \(Informationen zum Hinzufügen der Funktion zum konzeptionellen Modell finden Sie unter [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/de-de/0dad7b8b-58f6-4271-b238-f34810d68e5f).\)  
  
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/obj/x86/debug/edmxresourcestoembed/adventureworks.csdl#4)]
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/obj/x86/debug/edmxresourcestoembed/adventureworks.csdl#4)]
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#4)]  
  
## Beispiel  
 Mit dem folgenden Code wird der `AdventureWorksEntities`\-Klasse eine Methode hinzugefügt, die der konzeptionellen Modellfunktion oben zugeordnet wird.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#2)]
 [!code-vb[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#2)]  
  
## Beispiel  
 Im folgenden Code wird die Methode oben aufgerufen, um die Produkteinnahmen oben für ein angegebenes Produkt anzuzeigen:  
  
 [!code-csharp[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#3)]
 [!code-vb[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#3)]  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine modelldefinierte Funktion, die eine Auflistung \(als <xref:System.Linq.IQueryable%601>\-Objekt\) zurückgibt, aufgerufen wird.  Erwägen Sie den Einsatz der folgenden konzeptionellen Modellfunktion, die alle `SalesOrderDetails` für eine angegebene Produkt\-ID zurückgibt.  
  
 [!code-xml[DP L2E Methods on ObjectContext#7](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#7)]  
  
## Beispiel  
 Mit dem folgenden Code wird der `AdventureWorksEntities`\-Klasse eine Methode hinzugefügt, die der konzeptionellen Modellfunktion oben zugeordnet wird.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#8)]
 [!code-vb[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#8)]  
  
## Beispiel  
 Der folgende Code ruft die Methode auf.  Beachten Sie, dass die zurückgegebene <xref:System.Linq.IQueryable%601>\-Abfrage weiter verfeinert wird, um für jedes `SalesOrderDetail` Zeilengesamtbeträge zurückzugeben.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#9)]
 [!code-vb[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#9)]  
  
## Beispiel  
 **Aufrufen einer modelldefinierten Funktion als statische Methode für eine benutzerdefinierte Klasse**  
  
 Im nächsten Beispiel wird veranschaulicht, wie eine modelldefinierte Funktion als statische Methode für eine benutzerdefinierte Klasse aufgerufen wird.  Im Beispiel wird das [AdventureWorks Sales\-Modell](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832) verwendet.  
  
> [!NOTE]
>  Wenn Sie eine modelldefinierte Funktion als statische Methode für eine benutzerdefinierte Klasse aufrufen, muss die modelldefinierte Funktion eine Auflistung akzeptieren und eine Aggregation von Werten in der Auflistung zurückgeben.  
  
 Erwägen Sie die Verwendung der folgenden konzeptionellen Modellfunktion, die Produkteinnahmen für eine SalesOrderDetail\-Auflistung zurückgibt.  \(Informationen zum Hinzufügen der Funktion zum konzeptionellen Modell finden Sie unter [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/de-de/0dad7b8b-58f6-4271-b238-f34810d68e5f).\)  
  
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/obj/x86/debug/edmxresourcestoembed/adventureworks.csdl#1)]
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/obj/x86/debug/edmxresourcestoembed/adventureworks.csdl#1)]
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#1)]  
  
## Beispiel  
 Der folgende Code fügt der Anwendung eine Klasse hinzu, die eine statische Methode enthält, die der konzeptionellen Modellfunktion oben zugeordnet wird.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#5)]
 [!code-vb[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#5)]  
  
## Beispiel  
 Der folgenden Code ruft die Methode oben auf, um die Produkteinnahmen für eine SalesOrderDetail\-Auflistung anzuzeigen:  
  
 [!code-csharp[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#6)]
 [!code-vb[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#6)]  
  
## Siehe auch  
 [.edmx File Overview](http://msdn.microsoft.com/de-de/f4c8e7ce-1db6-417e-9759-15f8b55155d4)   
 [Abfragen in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)   
 [Aufrufen von Funktionen in LINQ to Entities\-Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)