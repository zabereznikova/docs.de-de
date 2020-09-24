---
title: 'Exemplarische Vorgehensweise: Beziehungsübergreifendes Abfragen (C#)'
ms.date: 03/30/2017
ms.assetid: 552abeb1-18f2-4e93-a9c6-ef7b2db30c32
ms.openlocfilehash: 9dfe34136f2d0a14a12f72e22a96d1882ddbce49
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164011"
---
# <a name="walkthrough-querying-across-relationships-c"></a><span data-ttu-id="069a2-102">Exemplarische Vorgehensweise: Beziehungsübergreifendes Abfragen (C#)</span><span class="sxs-lookup"><span data-stu-id="069a2-102">Walkthrough: Querying Across Relationships (C#)</span></span>

<span data-ttu-id="069a2-103">Diese exemplarische Vorgehensweise veranschaulicht die Verwendung von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *Zuordnungen* , um Fremdschlüssel Beziehungen in der Datenbank darzustellen.</span><span class="sxs-lookup"><span data-stu-id="069a2-103">This walkthrough demonstrates the use of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *associations* to represent foreign-key relationships in the database.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="069a2-104">Diese exemplarische Vorgehensweise wurde mithilfe von Visual C#-Entwicklungseinstellungen geschrieben.</span><span class="sxs-lookup"><span data-stu-id="069a2-104">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="069a2-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="069a2-105">Prerequisites</span></span>  

 <span data-ttu-id="069a2-106">Sie müssen Exemplarische Vorgehensweise [: einfaches Objektmodell und Abfrage (c#)](walkthrough-simple-object-model-and-query-csharp.md)abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="069a2-106">You must have completed [Walkthrough: Simple Object Model and Query (C#)](walkthrough-simple-object-model-and-query-csharp.md).</span></span> <span data-ttu-id="069a2-107">Diese exemplarische Vorgehensweise basiert auf jener und erfordert die Datei northwnd.mdf im Verzeichnis c:\linqtest5.</span><span class="sxs-lookup"><span data-stu-id="069a2-107">This walkthrough builds on that one, including the presence of the northwnd.mdf file in c:\linqtest5.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="069a2-108">Übersicht</span><span class="sxs-lookup"><span data-stu-id="069a2-108">Overview</span></span>  

 <span data-ttu-id="069a2-109">Diese exemplarische Vorgehensweise umfasst drei Hauptaufgaben:</span><span class="sxs-lookup"><span data-stu-id="069a2-109">This walkthrough consists of three main tasks:</span></span>  
  
- <span data-ttu-id="069a2-110">Hinzufügen einer Entitätsklasse zur Darstellung der Orders-Tabelle in der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="069a2-110">Adding an entity class to represent the Orders table in the sample Northwind database.</span></span>  
  
- <span data-ttu-id="069a2-111">Ergänzen von Anmerkungen zur `Customer`-Klasse, um die Beziehung zwischen der `Customer`-Klasse und der `Order`-Klasse zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="069a2-111">Supplementing annotations to the `Customer` class to enhance the relationship between the `Customer` and `Order` classes.</span></span>  
  
- <span data-ttu-id="069a2-112">Erstellen und Ausführen einer Abfrage, um das Abrufen von `Order`-Informationen unter Verwendung der `Customer`-Klasse zu testen</span><span class="sxs-lookup"><span data-stu-id="069a2-112">Creating and running a query to test obtaining `Order` information by using the `Customer` class.</span></span>  
  
## <a name="mapping-relationships-across-tables"></a><span data-ttu-id="069a2-113">Zuordnen von Beziehungen über Tabellen hinweg</span><span class="sxs-lookup"><span data-stu-id="069a2-113">Mapping Relationships Across Tables</span></span>  

 <span data-ttu-id="069a2-114">Erstellen Sie nach der Definition der `Customer`-Klasse die Definition der `Order`-Entitätsklasse, die den folgenden Code enthält. Dieser gibt an, dass `Order.Customer` ein Fremdschlüssel zu `Customer.CustomerID` ist.</span><span class="sxs-lookup"><span data-stu-id="069a2-114">After the `Customer` class definition, create the `Order` entity class definition that includes the following code, which indicates that `Order.Customer` relates as a foreign key to `Customer.CustomerID`.</span></span>  
  
### <a name="to-add-the-order-entity-class"></a><span data-ttu-id="069a2-115">So fügen Sie die Order-Entitätsklasse hinzu</span><span class="sxs-lookup"><span data-stu-id="069a2-115">To add the Order entity class</span></span>  
  
- <span data-ttu-id="069a2-116">Geben Sie den folgenden Code nach der `Customer`-Klasse ein, oder fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="069a2-116">Type or paste the following code after the `Customer` class:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#1)]  
  
## <a name="annotating-the-customer-class"></a><span data-ttu-id="069a2-117">Hinzufügen von Anmerkungen zu einer Customer-Klasse</span><span class="sxs-lookup"><span data-stu-id="069a2-117">Annotating the Customer Class</span></span>  

 <span data-ttu-id="069a2-118">In diesem Schritt fügen Sie der `Customer`-Klasse Anmerkungen hinzu, um deren Beziehung zur `Order`-Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="069a2-118">In this step, you annotate the `Customer` class to indicate its relationship to the `Order` class.</span></span> <span data-ttu-id="069a2-119">(Diese Ergänzung ist nicht unbedingt erforderlich, da die Definition der Beziehungen in beide Richtungen zum Erstellen der Verbindung ausreicht.</span><span class="sxs-lookup"><span data-stu-id="069a2-119">(This addition is not strictly necessary, because defining the relationship in either direction is sufficient to create the link.</span></span> <span data-ttu-id="069a2-120">Mithilfe dieser Anmerkung können Sie jedoch leicht in allen Richtungen zwischen den Objekten navigieren.)</span><span class="sxs-lookup"><span data-stu-id="069a2-120">But adding this annotation does enable you to easily navigate objects in either direction.)</span></span>  
  
### <a name="to-annotate-the-customer-class"></a><span data-ttu-id="069a2-121">So fügen Sie der Customer-Klasse Anmerkungen hinzu</span><span class="sxs-lookup"><span data-stu-id="069a2-121">To annotate the Customer class</span></span>  
  
- <span data-ttu-id="069a2-122">Geben Sie den folgenden Code in die `Customer`-Klasse ein, oder fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="069a2-122">Type or paste the following code into the `Customer` class:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#2)]  
  
## <a name="creating-and-running-a-query-across-the-customer-order-relationship"></a><span data-ttu-id="069a2-123">Erstellen und Ausführen einer Abfrage über die Customer-Order-Beziehung</span><span class="sxs-lookup"><span data-stu-id="069a2-123">Creating and Running a Query Across the Customer-Order Relationship</span></span>  

 <span data-ttu-id="069a2-124">Sie können nun direkt auf die `Order`-Objekte zugreifen, und zwar von den `Customer`-Objekten aus oder in umgekehrter Richtung.</span><span class="sxs-lookup"><span data-stu-id="069a2-124">You can now access `Order` objects directly from the `Customer` objects, or in the opposite order.</span></span> <span data-ttu-id="069a2-125">Sie benötigen keinen expliziten *Join* zwischen Kunden und Bestellungen.</span><span class="sxs-lookup"><span data-stu-id="069a2-125">You do not need an explicit *join* between customers and orders.</span></span>  
  
### <a name="to-access-order-objects-by-using-customer-objects"></a><span data-ttu-id="069a2-126">So greifen Sie mithilfe von Customer-Objekten auf Order-Objekte zu</span><span class="sxs-lookup"><span data-stu-id="069a2-126">To access Order objects by using Customer objects</span></span>  
  
1. <span data-ttu-id="069a2-127">Ändern Sie die `Main`-Methode durch das Eingeben oder Einfügen des folgenden Codes in die Methode:</span><span class="sxs-lookup"><span data-stu-id="069a2-127">Modify the `Main` method by typing or pasting the following code into the method:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#3)]  
  
2. <span data-ttu-id="069a2-128">Drücken Sie F5, um die Anwendung zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="069a2-128">Press F5 to debug your application.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="069a2-129">Sie können den SQL-Code im Konsolenfenster eliminieren, indem Sie `db.Log = Console.Out;` auskommentieren.</span><span class="sxs-lookup"><span data-stu-id="069a2-129">You can eliminate the SQL code in the Console window by commenting out `db.Log = Console.Out;`.</span></span>  
  
3. <span data-ttu-id="069a2-130">Drücken Sie die EINGABETASTE im Konsolenfenster, um das Debuggen zu stoppen.</span><span class="sxs-lookup"><span data-stu-id="069a2-130">Press Enter in the Console window to stop debugging.</span></span>  
  
## <a name="creating-a-strongly-typed-view-of-your-database"></a><span data-ttu-id="069a2-131">Erstellen einer Datenbankansicht mit strikter Typbindung</span><span class="sxs-lookup"><span data-stu-id="069a2-131">Creating a Strongly Typed View of Your Database</span></span>  

 <span data-ttu-id="069a2-132">Es ist viel leichter, mit einer Datenbankansicht mit strikter Typbindung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="069a2-132">It is much easier to start with a strongly typed view of your database.</span></span> <span data-ttu-id="069a2-133">Bei strikter Typbindung des <xref:System.Data.Linq.DataContext>-Objekts benötigen Sie keine Aufrufe von <xref:System.Data.Linq.DataContext.GetTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="069a2-133">By strongly typing the <xref:System.Data.Linq.DataContext> object, you do not need calls to <xref:System.Data.Linq.DataContext.GetTable%2A>.</span></span> <span data-ttu-id="069a2-134">Sie können Tabellen mit strikter Typbindung in allen Abfragen verwenden, wenn Sie das <xref:System.Data.Linq.DataContext>-Objekt mit strikter Typbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="069a2-134">You can use strongly typed tables in all your queries when you use the strongly typed <xref:System.Data.Linq.DataContext> object.</span></span>  
  
 <span data-ttu-id="069a2-135">In den folgenden Schritten erstellen Sie `Customers` als Tabelle mit strikter Typbindung und Zuordnung zur Customers-Tabelle in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="069a2-135">In the following steps, you will create `Customers` as a strongly typed table that maps to the Customers table in the database.</span></span>  
  
### <a name="to-strongly-type-the-datacontext-object"></a><span data-ttu-id="069a2-136">So erstellen Sie die striktre Typbindung für das DataContext-Objekt</span><span class="sxs-lookup"><span data-stu-id="069a2-136">To strongly type the DataContext object</span></span>  
  
1. <span data-ttu-id="069a2-137">Fügen Sie den folgenden Code oberhalb der Deklaration der `Customer`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="069a2-137">Add the following code above the `Customer` class declaration.</span></span>  
  
     [!code-csharp[DLinqWalk2CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#4)]  
  
2. <span data-ttu-id="069a2-138">Ändern Sie die `Main`-Methode wie folgt, damit diese den <xref:System.Data.Linq.DataContext> mit strikter Typbindung verwendet:</span><span class="sxs-lookup"><span data-stu-id="069a2-138">Modify the `Main` method to use the strongly typed <xref:System.Data.Linq.DataContext> as follows:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#5)]  
  
3. <span data-ttu-id="069a2-139">Drücken Sie F5, um die Anwendung zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="069a2-139">Press F5 to debug your application.</span></span>  
  
     <span data-ttu-id="069a2-140">Die Ausgabe im Konsolenfenster lautet:</span><span class="sxs-lookup"><span data-stu-id="069a2-140">The Console window output is:</span></span>  
  
     `ID=WHITC`  
  
4. <span data-ttu-id="069a2-141">Drücken Sie die EINGABETASTE im Konsolenfenster, um das Debuggen zu stoppen.</span><span class="sxs-lookup"><span data-stu-id="069a2-141">Press Enter in the console window to stop debugging.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="069a2-142">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="069a2-142">Next Steps</span></span>  

 <span data-ttu-id="069a2-143">In der nächsten exemplarischen Vorgehensweise (Exemplarische Vorgehensweise: Bearbeiten von[Daten (c#)](walkthrough-manipulating-data-csharp.md)) wird veranschaulicht, wie Daten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="069a2-143">The next walkthrough ([Walkthrough: Manipulating Data (C#)](walkthrough-manipulating-data-csharp.md)) demonstrates how to manipulate data.</span></span> <span data-ttu-id="069a2-144">Diese exemplarische Vorgehensweise setzt nicht voraus, dass Sie die beiden in dieser Serie abgeschlossenen exemplarischen Vorgehensweisen speichern.</span><span class="sxs-lookup"><span data-stu-id="069a2-144">That walkthrough does not require that you save the two walkthroughs in this series that you have already completed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="069a2-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="069a2-145">See also</span></span>

- [<span data-ttu-id="069a2-146">Lernen durch exemplarische Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="069a2-146">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
