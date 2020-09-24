---
title: 'Exemplarische Vorgehensweise: Beziehungsübergreifendes Abfragen (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: a7da43e3-769f-4e07-bcd6-552b8bde66f4
ms.openlocfilehash: ce5323b4ecd7bd0c4337d4632eff209e4d0ebd42
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163985"
---
# <a name="walkthrough-querying-across-relationships-visual-basic"></a><span data-ttu-id="feb39-102">Exemplarische Vorgehensweise: Beziehungsübergreifendes Abfragen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="feb39-102">Walkthrough: Querying Across Relationships (Visual Basic)</span></span>

<span data-ttu-id="feb39-103">Diese exemplarische Vorgehensweise veranschaulicht die Verwendung von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *Zuordnungen* , um Fremdschlüssel Beziehungen in der Datenbank darzustellen.</span><span class="sxs-lookup"><span data-stu-id="feb39-103">This walkthrough demonstrates the use of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *associations* to represent foreign-key relationships in the database.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="feb39-104">Diese exemplarische Vorgehensweise wurde mithilfe von Visual Basic-Entwicklungseinstellungen geschrieben.</span><span class="sxs-lookup"><span data-stu-id="feb39-104">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="feb39-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="feb39-105">Prerequisites</span></span>  

 <span data-ttu-id="feb39-106">Sie müssen Exemplarische Vorgehensweise [: einfaches Objektmodell und Abfrage (Visual Basic)](walkthrough-simple-object-model-and-query-visual-basic.md)abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="feb39-106">You must have completed [Walkthrough: Simple Object Model and Query (Visual Basic)](walkthrough-simple-object-model-and-query-visual-basic.md).</span></span> <span data-ttu-id="feb39-107">Diese exemplarische Vorgehensweise basiert auf diesem Schritt und erfordert die Datei northwnd.mdf im Verzeichnis c:\linqtest.</span><span class="sxs-lookup"><span data-stu-id="feb39-107">This walkthrough builds on that one, including the presence of the northwnd.mdf file in c:\linqtest.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="feb39-108">Übersicht</span><span class="sxs-lookup"><span data-stu-id="feb39-108">Overview</span></span>  

 <span data-ttu-id="feb39-109">Diese exemplarische Vorgehensweise umfasst drei Hauptaufgaben:</span><span class="sxs-lookup"><span data-stu-id="feb39-109">This walkthrough consists of three main tasks:</span></span>  
  
- <span data-ttu-id="feb39-110">Hinzufügen einer Entitätsklasse zur Darstellung der Orders-Tabelle in der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="feb39-110">Adding an entity class to represent the Orders table in the sample Northwind database.</span></span>  
  
- <span data-ttu-id="feb39-111">Ergänzen von Anmerkungen zur `Customer`-Klasse, um die Beziehung zwischen der `Customer`-Klasse und der `Order`-Klasse zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="feb39-111">Supplementing annotations to the `Customer` class to enhance the relationship between the `Customer` and `Order` classes.</span></span>  
  
- <span data-ttu-id="feb39-112">Erstellen und Ausführen einer Abfrage, um das Abrufen von `Order`-Informationen unter Verwendung der `Customer`-Klasse zu testen.</span><span class="sxs-lookup"><span data-stu-id="feb39-112">Creating and running a query to test the process of obtaining `Order` information by using the `Customer` class.</span></span>  
  
## <a name="mapping-relationships-across-tables"></a><span data-ttu-id="feb39-113">Zuordnen von Beziehungen über Tabellen hinweg</span><span class="sxs-lookup"><span data-stu-id="feb39-113">Mapping Relationships across Tables</span></span>  

 <span data-ttu-id="feb39-114">Erstellen Sie nach der Definition der `Customer`-Klasse die Definition der `Order`-Entitätsklasse, die den folgenden Code enthält. Dieser gibt an, dass `Orders.Customer` ein Fremdschlüssel zu `Customers.CustomerID` ist.</span><span class="sxs-lookup"><span data-stu-id="feb39-114">After the `Customer` class definition, create the `Order` entity class definition that includes the following code, which indicates that `Orders.Customer` relates as a foreign key to `Customers.CustomerID`.</span></span>  
  
#### <a name="to-add-the-order-entity-class"></a><span data-ttu-id="feb39-115">So fügen Sie die Order-Entitätsklasse hinzu</span><span class="sxs-lookup"><span data-stu-id="feb39-115">To add the Order entity class</span></span>  
  
- <span data-ttu-id="feb39-116">Geben Sie den folgenden Code nach der `Customer`-Klasse ein, oder fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="feb39-116">Type or paste the following code after the `Customer` class:</span></span>  
  
     [!code-vb[DLinqWalk2VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#1)]  
  
## <a name="annotating-the-customer-class"></a><span data-ttu-id="feb39-117">Hinzufügen von Anmerkungen zu einer Customer-Klasse</span><span class="sxs-lookup"><span data-stu-id="feb39-117">Annotating the Customer Class</span></span>  

 <span data-ttu-id="feb39-118">In diesem Schritt fügen Sie der `Customer`-Klasse Anmerkungen hinzu, um deren Beziehung zur `Order`-Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="feb39-118">In this step, you annotate the `Customer` class to indicate its relationship to the `Order` class.</span></span> <span data-ttu-id="feb39-119">(Diese Ergänzung ist nicht unbedingt erforderlich, da die Definition der Beziehungen in beide Richtungen zum Erstellen der Verbindung ausreicht.</span><span class="sxs-lookup"><span data-stu-id="feb39-119">(This addition is not strictly necessary, because defining the relationship in either direction is sufficient to create the link.</span></span> <span data-ttu-id="feb39-120">Mithilfe dieser Anmerkung können Sie jedoch leicht in allen Richtungen zwischen den Objekten navigieren.)</span><span class="sxs-lookup"><span data-stu-id="feb39-120">But adding this annotation does enable you to easily navigate objects in either direction.)</span></span>  
  
#### <a name="to-annotate-the-customer-class"></a><span data-ttu-id="feb39-121">So fügen Sie der Customer-Klasse Anmerkungen hinzu</span><span class="sxs-lookup"><span data-stu-id="feb39-121">To annotate the Customer class</span></span>  
  
- <span data-ttu-id="feb39-122">Geben Sie den folgenden Code in die `Customer`-Klasse ein, oder fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="feb39-122">Type or paste the following code into the `Customer` class:</span></span>  
  
     [!code-vb[DLinqWalk2VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#2)]  
  
## <a name="creating-and-running-a-query-across-the-customer-order-relationship"></a><span data-ttu-id="feb39-123">Erstellen und Ausführen einer Abfrage über die Customer-Order-Beziehung hinweg</span><span class="sxs-lookup"><span data-stu-id="feb39-123">Creating and Running a Query across the Customer-Order Relationship</span></span>  

 <span data-ttu-id="feb39-124">Sie können nun direkt auf die `Order`-Objekte zugreifen, und zwar von den `Customer`-Objekten aus oder in umgekehrter Richtung.</span><span class="sxs-lookup"><span data-stu-id="feb39-124">You can now access `Order` objects directly from the `Customer` objects, or in the opposite order.</span></span> <span data-ttu-id="feb39-125">Sie benötigen keinen expliziten *Join* zwischen Kunden und Bestellungen.</span><span class="sxs-lookup"><span data-stu-id="feb39-125">You do not need an explicit *join* between customers and orders.</span></span>  
  
#### <a name="to-access-order-objects-by-using-customer-objects"></a><span data-ttu-id="feb39-126">So greifen Sie mithilfe von Customer-Objekten auf Order-Objekte zu</span><span class="sxs-lookup"><span data-stu-id="feb39-126">To access Order objects by using Customer objects</span></span>  
  
1. <span data-ttu-id="feb39-127">Ändern Sie die `Sub Main`-Methode durch das Eingeben oder Einfügen des folgenden Codes in die Methode:</span><span class="sxs-lookup"><span data-stu-id="feb39-127">Modify the `Sub Main` method by typing or pasting the following code into the method:</span></span>  
  
     [!code-vb[DLinqWalk2VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#3)]  
  
2. <span data-ttu-id="feb39-128">Drücken Sie F5, um die Anwendung zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="feb39-128">Press F5 to debug your application.</span></span>  
  
     <span data-ttu-id="feb39-129">Zwei Namen werden im Meldungsfeld angezeigt, und das Konsolenfenster zeigt den generierten SQL-Code an.</span><span class="sxs-lookup"><span data-stu-id="feb39-129">Two names appear in the message box, and the Console window shows the generated SQL code.</span></span>  
  
3. <span data-ttu-id="feb39-130">Schließen Sie das Meldungsfeld, um das Debuggen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="feb39-130">Close the message box to stop debugging.</span></span>  
  
## <a name="creating-a-strongly-typed-view-of-your-database"></a><span data-ttu-id="feb39-131">Erstellen einer Datenbankansicht mit strikter Typbindung</span><span class="sxs-lookup"><span data-stu-id="feb39-131">Creating a Strongly Typed View of Your Database</span></span>  

 <span data-ttu-id="feb39-132">Es ist viel leichter, mit einer Datenbankansicht mit strikter Typbindung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="feb39-132">It is much easier to start with a strongly typed view of your database.</span></span> <span data-ttu-id="feb39-133">Bei strikter Typbindung des <xref:System.Data.Linq.DataContext>-Objekts benötigen Sie keine Aufrufe von <xref:System.Data.Linq.DataContext.GetTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="feb39-133">By strongly typing the <xref:System.Data.Linq.DataContext> object, you do not need calls to <xref:System.Data.Linq.DataContext.GetTable%2A>.</span></span> <span data-ttu-id="feb39-134">Sie können Tabellen mit strikter Typbindung in allen Abfragen verwenden, wenn Sie das <xref:System.Data.Linq.DataContext>-Objekt mit strikter Typbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="feb39-134">You can use strongly typed tables in all your queries when you use the strongly typed <xref:System.Data.Linq.DataContext> object.</span></span>  
  
 <span data-ttu-id="feb39-135">In den folgenden Schritten erstellen Sie `Customers` als Tabelle mit strikter Typbindung und Zuordnung zur Customers-Tabelle in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="feb39-135">In the following steps, you will create `Customers` as a strongly typed table that maps to the Customers table in the database.</span></span>  
  
#### <a name="to-strongly-type-the-datacontext-object"></a><span data-ttu-id="feb39-136">So erstellen Sie die striktre Typbindung für das DataContext-Objekt</span><span class="sxs-lookup"><span data-stu-id="feb39-136">To strongly type the DataContext object</span></span>  
  
1. <span data-ttu-id="feb39-137">Fügen Sie den folgenden Code oberhalb der Deklaration der `Customer`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="feb39-137">Add the following code above the `Customer` class declaration.</span></span>  
  
     [!code-vb[DLinqWalk2VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#4)]  
  
2. <span data-ttu-id="feb39-138">Ändern Sie die `Sub Main`-Methode wie folgt, damit diese den <xref:System.Data.Linq.DataContext> mit strikter Typbindung verwendet:</span><span class="sxs-lookup"><span data-stu-id="feb39-138">Modify `Sub Main` to use the strongly typed <xref:System.Data.Linq.DataContext> as follows:</span></span>  
  
     [!code-vb[DLinqWalk2VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#5)]  
  
3. <span data-ttu-id="feb39-139">Drücken Sie F5, um die Anwendung zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="feb39-139">Press F5 to debug your application.</span></span>  
  
     <span data-ttu-id="feb39-140">Die Ausgabe im Konsolenfenster lautet:</span><span class="sxs-lookup"><span data-stu-id="feb39-140">The Console window output is:</span></span>  
  
     `ID=WHITC`  
  
4. <span data-ttu-id="feb39-141">Drücken Sie die EINGABETASTE im Konsolenfenster, um die Anwendung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="feb39-141">Press Enter in the Console window to close the application.</span></span>  
  
5. <span data-ttu-id="feb39-142">Klicken Sie im Menü **Datei** auf **Alle speichern** , wenn Sie diese Anwendung speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="feb39-142">On the **File** menu, click **Save All** if you want to save this application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="feb39-143">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="feb39-143">Next Steps</span></span>  

 <span data-ttu-id="feb39-144">In der nächsten exemplarischen Vorgehensweise (Exemplarische Vorgehensweise: Bearbeiten von[Daten (Visual Basic)](walkthrough-manipulating-data-visual-basic.md)) wird veranschaulicht, wie Daten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="feb39-144">The next walkthrough ([Walkthrough: Manipulating Data (Visual Basic)](walkthrough-manipulating-data-visual-basic.md)) demonstrates how to manipulate data.</span></span> <span data-ttu-id="feb39-145">Diese exemplarische Vorgehensweise setzt nicht voraus, dass Sie die beiden in dieser Serie abgeschlossenen exemplarischen Vorgehensweisen speichern.</span><span class="sxs-lookup"><span data-stu-id="feb39-145">That walkthrough does not require that you save the two walkthroughs in this series that you have already completed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feb39-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="feb39-146">See also</span></span>

- [<span data-ttu-id="feb39-147">Lernen durch exemplarische Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="feb39-147">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
