---
title: Datenabruf und CUD-Operationen in n-schichtigen Anwendungen (LINQ to SQL)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c3133d53-83ed-4a4d-af8b-82edcf3831db
ms.openlocfilehash: 1bc97504b4dd053ce9ef747460a79865cbe836ee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197416"
---
# <a name="data-retrieval-and-cud-operations-in-n-tier-applications-linq-to-sql"></a><span data-ttu-id="0fdf0-102">Datenabruf und CUD-Operationen in n-schichtigen Anwendungen (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="0fdf0-102">Data Retrieval and CUD Operations in N-Tier Applications (LINQ to SQL)</span></span>

<span data-ttu-id="0fdf0-103">Wenn Sie Entitätsobjekte wie Customers oder Orders über ein Netzwerk an einen Client serialisieren, werden diese Entitäten von ihrem Datenkontext getrennt.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-103">When you serialize entity objects such as Customers or Orders to a client over a network, those entities are detached from their data context.</span></span> <span data-ttu-id="0fdf0-104">Änderungen oder Verknüpfungen mit anderen Objekten werden vom Datenkontext nicht mehr verfolgt.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-104">The data context no longer tracks their changes or their associations with other objects.</span></span> <span data-ttu-id="0fdf0-105">Dies stellt kein Problem dar, solange die Clients die Daten nur lesen.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-105">This is not an issue as long as the clients are only reading the data.</span></span> <span data-ttu-id="0fdf0-106">Es ist außerdem relativ einfach, Clients zu ermöglichen, einer Datenbank neue Zeilen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-106">It is also relatively simple to enable clients to add new rows to a database.</span></span> <span data-ttu-id="0fdf0-107">Wenn Ihre Anwendung jedoch voraussetzt, dass Clients Daten aktualisieren oder löschen sollen, müssen Sie die Entitäten an einen neuen Datenkontext anfügen, bevor Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-107">However, if your application requires that clients be able to update or delete data, then you must attach the entities to a new data context before you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0fdf0-108">Wenn Sie eine Überprüfung auf vollständige Parallelität mit ursprünglichen Werten verwenden, müssen Sie außerdem eine Möglichkeit schaffen, der Datenbank sowohl die ursprüngliche als auch die geänderte Entität bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-108">In addition, if you are using an optimistic concurrency check with original values, then you will also need a way to provide the database both the original entity and the entity as modified.</span></span> <span data-ttu-id="0fdf0-109">Die `Attach`-Methoden werden bereitgestellt, um es Ihnen zu ermöglichen, Entitäten in einen neuen Datenkontext einzufügen, nachdem sie getrennt wurden.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-109">The `Attach` methods are provided to enable you to put entities into a new data context after they have been detached.</span></span>  
  
 <span data-ttu-id="0fdf0-110">Auch wenn Sie Proxy Objekte anstelle der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Entitäten serialisieren, müssen Sie immer noch eine Entität auf der Datenzugriffs Schicht (Data Access Layer, DAL) erstellen und Sie an einen neuen anfügen <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> , um die Daten an die Datenbank zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-110">Even if you are serializing proxy objects in place of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] entities, you still have to construct an entity on the data access layer (DAL), and attach it to a new <xref:System.Data.Linq.DataContext?displayProperty=nameWithType>, in order to submit the data to the database.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0fdf0-111">ist vollständig für die Serialisierung von Entitäten nicht gleich.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-111">is completely indifferent about how entities are serialized.</span></span> <span data-ttu-id="0fdf0-112">Weitere Informationen zur Verwendung der objektrelationaler Designer-und SQLMetal-Tools zum Generieren von Klassen, die mit Windows Communication Foundation (WCF) serialisierbar sind, finden Sie unter Gewusst [wie: Erstellen von serialisierbaren Entitäten](how-to-make-entities-serializable.md).</span><span class="sxs-lookup"><span data-stu-id="0fdf0-112">For more information about how to use the Object Relational Designer and SQLMetal tools to generate classes that are serializable by using Windows Communication Foundation (WCF), see [How to: Make Entities Serializable](how-to-make-entities-serializable.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fdf0-113">Rufen Sie die `Attach`-Methoden nur für neue oder deserialisierte Entitäten auf.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-113">Only call the `Attach` methods on new or deserialized entities.</span></span> <span data-ttu-id="0fdf0-114">Die einzige Möglichkeit, eine Entität von ihrem ursprünglichen Datenkontext zu trennen, besteht darin, sie zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-114">The only way for an entity to be detached from its original data context is for it to be serialized.</span></span> <span data-ttu-id="0fdf0-115">Wenn Sie versuchen, eine nicht getrennte Entität an einen neuen Datenkontext anzufügen, und diese Entität noch über verzögerte Ladeprogramme aus dem vorherigen Datenkontext verfügt, löst [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-115">If you try to attach an undetached entity to a new data context, and that entity still has deferred loaders from its previous data context, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] will thrown an exception.</span></span> <span data-ttu-id="0fdf0-116">Eine Entität mit verzögerten Ladenprogrammen aus zwei unterschiedlichen Datenkontexten könnte unerwünschte Ergebnisse hervorbringen, wenn Sie Einfüge-, Aktualisierungs- und Löschvorgänge für diese Entität ausführen.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-116">An entity with deferred loaders from two different data contexts could cause unwanted results when you perform insert, update, and delete operations on that entity.</span></span> <span data-ttu-id="0fdf0-117">Weitere Informationen zu verzögerten Lade Programmen finden Sie unter [Verzögertes oder sofortiges Laden](deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="0fdf0-117">For more information about deferred loaders, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="retrieving-data"></a><span data-ttu-id="0fdf0-118">Abrufen von Daten</span><span class="sxs-lookup"><span data-stu-id="0fdf0-118">Retrieving Data</span></span>  
  
### <a name="client-method-call"></a><span data-ttu-id="0fdf0-119">Clientmethodenaufruf</span><span class="sxs-lookup"><span data-stu-id="0fdf0-119">Client Method Call</span></span>  

 <span data-ttu-id="0fdf0-120">In den folgenden Beispielen wird ein Beispielmethodenaufruf der DAL von einem Windows Forms-Client aus veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-120">The following examples show a sample method call to the DAL from a Windows Forms client.</span></span> <span data-ttu-id="0fdf0-121">Die DAL wird in diesem Beispiel als Windows-Dienstbibliothek implementiert:</span><span class="sxs-lookup"><span data-stu-id="0fdf0-121">In this example, the DAL is implemented as a Windows Service Library:</span></span>  
  
```vb  
Private Function GetProdsByCat_Click(ByVal sender As Object, ByVal e _  
    As EventArgs)  
  
    ' Create the WCF client proxy.  
    Dim proxy As New NorthwindServiceReference.Service1Client  
  
    ' Call the method on the service.  
    Dim products As NorthwindServiceReference.Product() = _  
        proxy.GetProductsByCategory(1)  
  
    ' If the database uses original values for concurrency checks,  
    ' the client needs to store them and pass them back to the  
    ' middle tier along with the new values when updating data.  
  
    For Each v As NorthwindClient1.NorthwindServiceReference.Product _  
        In products  
        ' Persist to a List(Of Product) declared at class scope.  
        ' Additional change-tracking logic is the responsibility  
        ' of the presentation tier and/or middle tier.  
        originalProducts.Add(v)  
    Next  
  
    ' (Not shown) Bind the products list to a control  
    ' and/or perform whatever processing is necessary.  
End Function  
```  
  
```csharp  
private void GetProdsByCat_Click(object sender, EventArgs e)  
{  
    // Create the WCF client proxy.  
    NorthwindServiceReference.Service1Client proxy =
    new NorthwindClient.NorthwindServiceReference.Service1Client();  
  
    // Call the method on the service.  
    NorthwindServiceReference.Product[] products =
    proxy.GetProductsByCategory(1);  
  
    // If the database uses original values for concurrency checks,
    // the client needs to store them and pass them back to the
    // middle tier along with the new values when updating data.  
    foreach (var v in products)  
    {  
        // Persist to a list<Product> declared at class scope.  
        // Additional change-tracking logic is the responsibility  
        // of the presentation tier and/or middle tier.  
        originalProducts.Add(v);  
    }  
  
    // (Not shown) Bind the products list to a control  
    // and/or perform whatever processing is necessary.  
    }  
```  
  
### <a name="middle-tier-implementation"></a><span data-ttu-id="0fdf0-122">Implementierung auf der mittleren Ebene</span><span class="sxs-lookup"><span data-stu-id="0fdf0-122">Middle Tier Implementation</span></span>  

 <span data-ttu-id="0fdf0-123">Im folgenden Beispiel wird eine Implementierung der Schnittstellenmethode auf der mittleren Ebene veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-123">The following example shows an implementation of the interface method on the middle tier.</span></span> <span data-ttu-id="0fdf0-124">Die folgenden beiden Hauptpunkte sind zu beachten:</span><span class="sxs-lookup"><span data-stu-id="0fdf0-124">The following are the two main points to note:</span></span>  
  
- <span data-ttu-id="0fdf0-125"><xref:System.Data.Linq.DataContext> wird im Methodenbereich deklariert.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-125">The <xref:System.Data.Linq.DataContext> is declared at method scope.</span></span>  
  
- <span data-ttu-id="0fdf0-126">Die Methode gibt eine <xref:System.Collections.IEnumerable>-Auflistung der tatsächlichen Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-126">The method returns an <xref:System.Collections.IEnumerable> collection of the actual results.</span></span> <span data-ttu-id="0fdf0-127">Das Serialisierungsprogramm führt die Abfrage aus, um die Ergebnisse an die Client- oder Präsentationsebene zurückzusenden.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-127">The serializer will execute the query to send the results back to the client/presentation tier.</span></span> <span data-ttu-id="0fdf0-128">Um lokal auf der mittleren Ebene auf die Abfrageergebnisse zuzugreifen, können Sie die Ausführung erzwingen, indem Sie `ToList` oder `ToArray` für die Abfragevariable aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-128">To access the query results locally on the middle tier, you can force execution by calling `ToList` or `ToArray` on the query variable.</span></span> <span data-ttu-id="0fdf0-129">Anschließend können Sie diese Liste oder dieses Array als `IEnumerable` zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-129">You can then return that list or array as an `IEnumerable`.</span></span>  
  
```vb  
Public Function GetProductsByCategory(ByVal categoryID As Integer) _  
    As IEnumerable(Of Product)  
  
    Dim db As New NorthwindClasses1DataContext(connectionString)  
    Dim productQuery = _  
    From prod In db.Products _  
    Where prod.CategoryID = categoryID _  
    Select prod  
  
    Return productQuery.AsEnumerable()  
  
End Function  
```  
  
```csharp  
public IEnumerable<Product> GetProductsByCategory(int categoryID)  
{  
    NorthwindClasses1DataContext db =
    new NorthwindClasses1DataContext(connectionString);  
  
    IEnumerable<Product> productQuery =  
    from prod in db.Products  
    where prod.CategoryID == categoryID  
    select prod;  
  
    return productQuery.AsEnumerable();
}  
```  
  
 <span data-ttu-id="0fdf0-130">Eine Instanz eines Datenkontexts sollte eine Lebensdauer von einer "Arbeitseinheit" haben.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-130">An instance of a data context should have a lifetime of one "unit of work."</span></span> <span data-ttu-id="0fdf0-131">In einer lose verknüpften Umgebung ist eine Arbeitseinheit normalerweise klein und entspricht vielleicht einer vollständigen Transaktion, einschließlich eines einzelnen Aufrufs von `SubmitChanges`.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-131">In a loosely-coupled environment, a unit of work is typically small, perhaps one optimistic transaction, including a single call to `SubmitChanges`.</span></span> <span data-ttu-id="0fdf0-132">Der Datenkontext wird deshalb im Methodenbereich erstellt und freigegeben.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-132">Therefore, the data context is created and disposed at method scope.</span></span> <span data-ttu-id="0fdf0-133">Wenn die Arbeitseinheit Aufrufe einer Geschäftsregellogik einschließt, behalten Sie die `DataContext`-Instanz im Allgemeinen für die gesamte Operation bei.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-133">If the unit of work includes calls to business rules logic, then generally you will want to keep the `DataContext` instance for that whole operation.</span></span> <span data-ttu-id="0fdf0-134">`DataContext`-Instanzen sind grundsätzlich nicht dafür vorgesehen, über einen längeren Zeitraum für eine beliebige Anzahl von Transaktionen beibehalten zu werden.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-134">In any case, `DataContext` instances are not intended to be kept alive for long periods of time across arbitrary numbers of transactions.</span></span>  
  
 <span data-ttu-id="0fdf0-135">Diese Methode gibt Product-Objekte, aber keine Auflistung von Order_Detail-Objekten zurück, die mit den einzelnen Produkten verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-135">This method will return Product objects but not the collection of Order_Detail objects that are associated with each Product.</span></span> <span data-ttu-id="0fdf0-136">Verwenden Sie das <xref:System.Data.Linq.DataLoadOptions>-Objekt, um dieses Standardverhalten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-136">Use the <xref:System.Data.Linq.DataLoadOptions> object to change this default behavior.</span></span> <span data-ttu-id="0fdf0-137">Weitere Informationen finden Sie unter Gewusst [wie: Steuern, wie viele verwandte Daten abgerufen](how-to-control-how-much-related-data-is-retrieved.md)werden.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-137">For more information, see [How to: Control How Much Related Data Is Retrieved](how-to-control-how-much-related-data-is-retrieved.md).</span></span>  
  
## <a name="inserting-data"></a><span data-ttu-id="0fdf0-138">Einfügen von Daten</span><span class="sxs-lookup"><span data-stu-id="0fdf0-138">Inserting Data</span></span>  

 <span data-ttu-id="0fdf0-139">Um ein neues Objekt einzufügen, ruft die Präsentationsebene nur die relevante Methode für die Schnittstelle der mittleren Ebene auf und übergibt das neue einzufügende Objekt.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-139">To insert a new object, the presentation tier just calls the relevant method on the middle tier interface, and passes in the new object to insert.</span></span> <span data-ttu-id="0fdf0-140">In einigen Fällen kann es effizienter sein, wenn der Client nur einige Werte übergibt und das Erstellen des vollständigen Objekts der mittleren Ebene überlässt.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-140">In some cases, it may be more efficient for the client to pass in only some values and have the middle tier construct the full object.</span></span>  
  
### <a name="middle-tier-implementation"></a><span data-ttu-id="0fdf0-141">Implementierung auf der mittleren Ebene</span><span class="sxs-lookup"><span data-stu-id="0fdf0-141">Middle Tier Implementation</span></span>  

 <span data-ttu-id="0fdf0-142">Auf der mittleren Ebene wird ein neuer <xref:System.Data.Linq.DataContext> erstellt, das Objekt mithilfe der <xref:System.Data.Linq.DataContext>-Methode an <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> angefügt und das Objekt beim Aufrufen von <xref:System.Data.Linq.DataContext.SubmitChanges%2A> eingefügt.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-142">On the middle tier, a new <xref:System.Data.Linq.DataContext> is created, the object is attached to the <xref:System.Data.Linq.DataContext> by using the <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> method, and the object is inserted when <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called.</span></span> <span data-ttu-id="0fdf0-143">Ausnahmen, Rückrufe und Fehlerbedingungen können wie in jedem beliebigen anderen Webdienstszenario behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-143">Exceptions, callbacks, and error conditions can be handled just as in any other Web service scenario.</span></span>  
  
```vb  
' No call to Attach is necessary for inserts.  
Public Sub InsertOrder(ByVal o As Order)  
  
    Dim db As New NorthwindClasses1DataContext(connectionString)  
    db.Orders.InsertOnSubmit(o)  
  
    ' Exception handling not shown.  
    db.SubmitChanges()  
  
End Sub  
```  
  
```csharp  
// No call to Attach is necessary for inserts.  
    public void InsertOrder(Order o)  
    {  
        NorthwindClasses1DataContext db = new NorthwindClasses1DataContext(connectionString);  
        db.Orders.InsertOnSubmit(o);  
  
        // Exception handling not shown.  
        db.SubmitChanges();  
    }  
```  
  
## <a name="deleting-data"></a><span data-ttu-id="0fdf0-144">Löschen von Daten</span><span class="sxs-lookup"><span data-stu-id="0fdf0-144">Deleting Data</span></span>  

 <span data-ttu-id="0fdf0-145">Um ein vorhandenes Objekt aus der Datenbank zu löschen, ruft die Präsentationsebene die relevante Methode für die Schnittstelle der mittleren Ebene auf und übergibt eine Kopie, in der die ursprünglichen Werte des zu löschenden Objekts enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-145">To delete an existing object from the database, the presentation tier calls the relevant method on the middle tier interface, and passes in its copy that includes original values of the object to be deleted.</span></span>  
  
 <span data-ttu-id="0fdf0-146">Löschvorgänge umfassen Überprüfungen auf vollständige Parallelität, und das zu löschende Objekt muss zuerst an den neuen Datenkontext angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-146">Delete operations involve optimistic concurrency checks, and the object to be deleted must first be attached to the new data context.</span></span> <span data-ttu-id="0fdf0-147">In diesem Beispiel wird der `Boolean`-Parameter auf `false` festgelegt, um anzuzeigen, dass das Objekt über keinen Timestamp (RowVersion) verfügt.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-147">In this example, the `Boolean` parameter is set to `false` to indicate that the object does not have a timestamp (RowVersion).</span></span> <span data-ttu-id="0fdf0-148">Wenn die Datenbanktabelle Timestamps für jeden Datensatz generiert, sind Überprüfungen auf Parallelität besonders für den Client bedeutend einfacher auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-148">If your database table does generate timestamps for each record, then concurrency checks are much simpler, especially for the client.</span></span> <span data-ttu-id="0fdf0-149">Übergeben Sie entweder das ursprüngliche oder geänderte Objekt, und legen Sie den `Boolean`-Parameter auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-149">Just pass in either the original or modified object and set the `Boolean` parameter to `true`.</span></span> <span data-ttu-id="0fdf0-150">Auf der mittleren Ebene ist es grundsätzlich erforderlich, die <xref:System.Data.Linq.ChangeConflictException> abzufangen.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-150">In any case, on the middle tier it is typically necessary to catch the <xref:System.Data.Linq.ChangeConflictException>.</span></span> <span data-ttu-id="0fdf0-151">Weitere Informationen zum Behandeln von Konflikten bei der vollständigen Parallelität finden Sie unter [optimistische Parallelität: Übersicht](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0fdf0-151">For more information about how to handle optimistic concurrency conflicts, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
 <span data-ttu-id="0fdf0-152">Beim Löschen von Entitäten, die über Fremdschlüsseleinschränkungen für verknüpfte Tabellen verfügen, müssen Sie zuerst alle Objekte in den zugehörigen <xref:System.Data.Linq.EntitySet%601>-Auflistungen löschen.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-152">When deleting entities that have foreign key constraints on associated tables, you must first delete all the objects in its <xref:System.Data.Linq.EntitySet%601> collections.</span></span>  
  
```vb  
' Attach is necessary for deletes.  
Public Sub DeleteOrder(ByVal order As Order)  
    Dim db As New NorthwindClasses1DataContext(connectionString)  
  
    db.Orders.Attach(order, False)  
    ' This will throw an exception if the order has order details.  
    db.Orders.DeleteOnSubmit(order)  
  
    Try  
        ' ConflictMode is an optional parameter.  
        db.SubmitChanges(ConflictMode.ContinueOnConflict)  
  
    Catch ex As ChangeConflictException  
        ' Get conflict information, and take actions  
        ' that are appropriate for your application.  
        ' See MSDN Article "How to: Manage Change  
        ' Conflicts (LINQ to SQL).  
  
    End Try  
End Sub  
```  
  
```csharp  
// Attach is necessary for deletes.  
public void DeleteOrder(Order order)  
{  
    NorthwindClasses1DataContext db = new NorthwindClasses1DataContext(connectionString);  
  
    db.Orders.Attach(order, false);  
    // This will throw an exception if the order has order details.  
    db.Orders.DeleteOnSubmit(order);  
    try  
    {  
        // ConflictMode is an optional parameter.  
        db.SubmitChanges(ConflictMode.ContinueOnConflict);  
    }  
    catch (ChangeConflictException e)  
    {  
       // Get conflict information, and take actions  
       // that are appropriate for your application.  
       // See MSDN Article How to: Manage Change Conflicts (LINQ to SQL).  
    }  
}  
```  
  
## <a name="updating-data"></a><span data-ttu-id="0fdf0-153">Aktualisieren von Daten</span><span class="sxs-lookup"><span data-stu-id="0fdf0-153">Updating Data</span></span>  

 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0fdf0-154">unterstützt Updates in folgenden Szenarien mit vollständiger Parallelität:</span><span class="sxs-lookup"><span data-stu-id="0fdf0-154">supports updates in these scenarios involving optimistic concurrency:</span></span>  
  
- <span data-ttu-id="0fdf0-155">Vollständige Parallelität auf der Grundlage von Timestamps oder RowVersion-Nummern</span><span class="sxs-lookup"><span data-stu-id="0fdf0-155">Optimistic concurrency based on timestamps or RowVersion numbers.</span></span>  
  
- <span data-ttu-id="0fdf0-156">Vollständige Parallelität auf der Grundlage ursprünglicher Werte einer Teilmenge von Entitätseigenschaften</span><span class="sxs-lookup"><span data-stu-id="0fdf0-156">Optimistic concurrency based on original values of a subset of entity properties.</span></span>  
  
- <span data-ttu-id="0fdf0-157">Vollständige Parallelität auf der Grundlage der vollständigen ursprünglichen und geänderten Entitäten</span><span class="sxs-lookup"><span data-stu-id="0fdf0-157">Optimistic concurrency based on the complete original and modified entities.</span></span>  
  
 <span data-ttu-id="0fdf0-158">Sie können auch Update- oder Löschvorgänge für eine Entität und ihre Beziehungen ausführen, beispielsweise für einen Kunden und eine Auflistung der zugehörigen Bestellobjekte.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-158">You can also perform updates or deletes on an entity together with its relations, for example a Customer and a collection of its associated Order objects.</span></span> <span data-ttu-id="0fdf0-159">Wenn Sie auf dem Client Änderungen an einem Diagramm von Entitätsobjekten und deren untergeordneten (`EntitySet`) Auflistungen vornehmen und für Überprüfungen auf vollständige Parallelität ursprüngliche Werte erforderlich sind, muss der Client diese ursprünglichen Werte für jede Entität und jedes <xref:System.Data.Linq.EntitySet%601>-Objekt bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-159">When you make modifications on the client to a graph of entity objects and their child (`EntitySet`) collections, and the optimistic concurrency checks require original values, the client must provide those original values for each entity and <xref:System.Data.Linq.EntitySet%601> object.</span></span> <span data-ttu-id="0fdf0-160">Wenn Clients in der Lage sein sollen, eine Reihe verknüpfter Updates, Löschungen und Einfügungen in einem einzelnen Methodenaufruf auszuführen, müssen Sie auf dem Client eine Möglichkeit vorsehen, um anzuzeigen, welcher Operationstyp für welche Entität ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-160">If you want to enable clients to make a set of related updates, deletes, and insertions in a single method call, you must provide the client a way to indicate what type of operation to perform on each entity.</span></span> <span data-ttu-id="0fdf0-161">Auf der mittleren Ebene müssen Sie anschließend die geeignete <xref:System.Data.Linq.ITable.Attach%2A>-Methode und dann <xref:System.Data.Linq.ITable.InsertOnSubmit%2A>, <xref:System.Data.Linq.ITable.DeleteAllOnSubmit%2A> oder <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> (ohne `Attach`, für Einfügungen) für jede Entität aufrufen, bevor Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-161">On the middle tier, you then must call the appropriate <xref:System.Data.Linq.ITable.Attach%2A> method and then <xref:System.Data.Linq.ITable.InsertOnSubmit%2A>, <xref:System.Data.Linq.ITable.DeleteAllOnSubmit%2A>, or <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> (without `Attach`, for insertions) for each entity before you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="0fdf0-162">Das Abrufen von Daten aus der Datenbank ist keine zulässige Methode, um ursprüngliche Werte zu erhalten, bevor Sie ein Update versuchen.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-162">Do not retrieve data from the database as a way to obtain original values before you try updates.</span></span>  
  
 <span data-ttu-id="0fdf0-163">Weitere Informationen zur vollständigen Parallelität finden Sie unter [optimistische Parallelität: Übersicht](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0fdf0-163">For more information about optimistic concurrency, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span> <span data-ttu-id="0fdf0-164">Ausführliche Informationen zum Auflösen von Konflikten bei der vollständigen Parallelität finden Sie unter Gewusst [wie: Verwalten von Änderungs Konflikten](how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="0fdf0-164">For detailed information about resolving optimistic concurrency change conflicts, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>  
  
 <span data-ttu-id="0fdf0-165">In den folgenden Beispielen werden die einzelnen Szenarien veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="0fdf0-165">The following examples demonstrate each scenario:</span></span>  
  
### <a name="optimistic-concurrency-with-timestamps"></a><span data-ttu-id="0fdf0-166">Vollständige Parallelität mit Timestamps</span><span class="sxs-lookup"><span data-stu-id="0fdf0-166">Optimistic concurrency with timestamps</span></span>  
  
```vb  
' Assume that "customer" has been sent by client.  
' Attach with "true" to say this is a modified entity  
' and it can be checked for optimistic concurrency  
' because it has a column that is marked with the  
' "RowVersion" attribute.  
  
db.Customers.Attach(customer, True)  
  
Try  
    ' Optional: Specify a ConflictMode value  
    ' in call to SubmitChanges.  
    db.SubmitChanges()  
Catch ex As ChangeConflictException  
    ' Handle conflict based on options provided.  
    ' See MSDN article "How to: Manage Change  
    ' Conflicts (LINQ to SQL)".  
End Try  
```  
  
```csharp  
// Assume that "customer" has been sent by client.  
// Attach with "true" to say this is a modified entity  
// and it can be checked for optimistic concurrency because  
//  it has a column that is marked with "RowVersion" attribute  
db.Customers.Attach(customer, true)  
try  
{  
    // Optional: Specify a ConflictMode value  
    // in call to SubmitChanges.  
    db.SubmitChanges();  
}  
catch(ChangeConflictException e)  
{  
    // Handle conflict based on options provided  
    // See MSDN article How to: Manage Change Conflicts (LINQ to SQL).  
}  
```  
  
### <a name="with-subset-of-original-values"></a><span data-ttu-id="0fdf0-167">Mit einer Teilmenge ursprünglicher Werte</span><span class="sxs-lookup"><span data-stu-id="0fdf0-167">With Subset of Original Values</span></span>  

 <span data-ttu-id="0fdf0-168">Bei dieser Vorgehensweise gibt der Client das vollständige serialisierte Objekt zusammen mit den zu ändernden Werten zurück.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-168">In this approach, the client returns the complete serialized object, together with the values to be modified.</span></span>  
  
```vb  
Public Sub UpdateProductInventory(ByVal p As Product, ByVal _  
    unitsInStock As Short?, ByVal unitsOnOrder As Short?)  
  
    Using db As New NorthwindClasses1DataContext(connectionString)  
        ' p is the original unmodified product  
        ' that was obtained from the database.  
        ' The client kept a copy and returns it now.  
        db.Products.Attach(p, False)  
  
        ' Now that the original values are in the data context,  
        ' apply the changes.  
        p.UnitsInStock = unitsInStock  
        p.UnitsOnOrder = unitsOnOrder  
  
        Try  
            ' Optional: Specify a ConflictMode value  
            ' in call to SubmitChanges.  
            db.SubmitChanges()  
  
        Catch ex As Exception  
            ' Handle conflict based on options provided.  
            ' See MSDN article "How to: Manage Change Conflicts  
            ' (LINQ to SQL)".  
        End Try  
    End Using  
End Sub  
```  
  
```csharp  
public void UpdateProductInventory(Product p, short? unitsInStock, short? unitsOnOrder)  
{  
    using (NorthwindClasses1DataContext db = new NorthwindClasses1DataContext(connectionString))  
    {  
        // p is the original unmodified product  
        // that was obtained from the database.  
        // The client kept a copy and returns it now.  
        db.Products.Attach(p, false);  
  
        // Now that the original values are in the data context, apply the changes.  
        p.UnitsInStock = unitsInStock;  
        p.UnitsOnOrder = unitsOnOrder;  
        try  
        {  
             // Optional: Specify a ConflictMode value  
             // in call to SubmitChanges.  
             db.SubmitChanges();  
        }  
        catch (ChangeConflictException e)  
        {  
            // Handle conflict based on provided options.  
            // See MSDN article How to: Manage Change Conflicts  
            // (LINQ to SQL).  
        }  
    }  
}  
```  
  
### <a name="with-complete-entities"></a><span data-ttu-id="0fdf0-169">Mit vollständigen Entitäten</span><span class="sxs-lookup"><span data-stu-id="0fdf0-169">With Complete Entities</span></span>  
  
```vb  
Public Sub UpdateProductInfo(ByVal newProd As Product, ByVal _  
    originalProd As Product)  
  
    Using db As New NorthwindClasses1DataContext(connectionString)  
        db.Products.Attach(newProd, originalProd)  
  
        Try  
            ' Optional: Specify a ConflictMode value  
            ' in call to SubmitChanges.  
            db.SubmitChanges()  
  
        Catch ex As Exception  
            ' Handle potential change conflicgt in whatever way  
            ' is appropriate for your application.  
            ' For more information, see the MSDN article  
            ' "How to: Manage Change Conflicts (LINQ to  
            ' SQL)".  
        End Try  
  
    End Using  
End Sub  
```  
  
```csharp  
public void UpdateProductInfo(Product newProd, Product originalProd)  
{  
     using (NorthwindClasses1DataContext db = new  
        NorthwindClasses1DataContext(connectionString))  
     {  
         db.Products.Attach(newProd, originalProd);  
         try  
         {  
               // Optional: Specify a ConflictMode value  
               // in call to SubmitChanges.  
               db.SubmitChanges();  
         }  
        catch (ChangeConflictException e)  
        {  
            // Handle potential change conflict in whatever way  
            // is appropriate for your application.  
            // For more information, see the MSDN article  
            // How to: Manage Change Conflicts (LINQ to SQL)/  
        }
    }  
}  
```  
  
 <span data-ttu-id="0fdf0-170">Um eine Auflistung zu aktualisieren, rufen Sie <xref:System.Data.Linq.ITable.AttachAll%2A> anstelle von `Attach` auf.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-170">To update a collection, call <xref:System.Data.Linq.ITable.AttachAll%2A> instead of `Attach`.</span></span>  
  
### <a name="expected-entity-members"></a><span data-ttu-id="0fdf0-171">Erwartete Entitätsmember</span><span class="sxs-lookup"><span data-stu-id="0fdf0-171">Expected Entity Members</span></span>  

 <span data-ttu-id="0fdf0-172">Wie bereits erwähnt, müssen nur bestimmte Member des Entitätsobjekts festgelegt werden, bevor Sie die `Attach`-Methoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-172">As stated previously, only certain members of the entity object are required to be set before you call the `Attach` methods.</span></span> <span data-ttu-id="0fdf0-173">Entitätsmember, die festgelegt werden müssen, sollten folgenden Kriterien erfüllen:</span><span class="sxs-lookup"><span data-stu-id="0fdf0-173">Entity members that are required to be set must fulfill the following criteria:</span></span>  
  
- <span data-ttu-id="0fdf0-174">Sie müssen Teil der Identität der Entität sein.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-174">Be part of the entity’s identity.</span></span>  
  
- <span data-ttu-id="0fdf0-175">Von ihnen wird erwartet, dass sie sich ändern.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-175">Be expected to be modified.</span></span>  
  
- <span data-ttu-id="0fdf0-176">Es muss sich um einen Timestamp handeln oder ihr <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Attribut muss auf einen anderen Wert als `Never` festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-176">Be a timestamp or have its <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> attribute set to something besides `Never`.</span></span>  
  
 <span data-ttu-id="0fdf0-177">Wenn eine Tabelle einen Timestamp oder eine Versionsnummer für die Prüfung auf vollständige Parallelität verwendet, müssen diese Member daher festgelegt sein, bevor Sie <xref:System.Data.Linq.ITable.Attach%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-177">If a table uses a timestamp or version number for an optimistic concurrency check, you must set those members before you call <xref:System.Data.Linq.ITable.Attach%2A>.</span></span> <span data-ttu-id="0fdf0-178">Ein Member gilt als für die Überprüfung auf vollständige Parallelität festgelegt, wenn die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>-Eigenschaft für dieses Spaltenattribut auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-178">A member is dedicated for optimistic concurrency checking when the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property is set to true on that Column attribute.</span></span> <span data-ttu-id="0fdf0-179">Alle angeforderten Updates werden nur gesendet, wenn der Wert für die Versionsnummer oder den Timestamp in Datenbank identisch ist.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-179">Any requested updates will be submitted only if the version number or timestamp values are the same on the database.</span></span>  
  
 <span data-ttu-id="0fdf0-180">Member werden ebenfalls in der Überprüfung auf vollständige Parallelität verwendet, solange <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> für den Member nicht auf `Never` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-180">A member is also used in the optimistic concurrency check as long as the member does not have <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> set to `Never`.</span></span> <span data-ttu-id="0fdf0-181">Sofern nicht anders angegeben, lautet der Standardwert `Always`.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-181">The default value is `Always` if no other value is specified.</span></span>  
  
 <span data-ttu-id="0fdf0-182">Wenn einer dieser erforderlichen Member fehlt, wird während <xref:System.Data.Linq.ChangeConflictException> ("Zeile nicht gefunden oder geändert") eine <xref:System.Data.Linq.DataContext.SubmitChanges%2A> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-182">If any one of these required members is missing, a <xref:System.Data.Linq.ChangeConflictException> is thrown during <xref:System.Data.Linq.DataContext.SubmitChanges%2A> ("Row not found or changed").</span></span>  
  
### <a name="state"></a><span data-ttu-id="0fdf0-183">State</span><span class="sxs-lookup"><span data-stu-id="0fdf0-183">State</span></span>  

 <span data-ttu-id="0fdf0-184">Nachdem ein Entitätsobjekt an die <xref:System.Data.Linq.DataContext>-Instanz angefügt wurde, wird davon ausgegangen, dass sich das Objekt im `PossiblyModified`-Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-184">After an entity object is attached to the <xref:System.Data.Linq.DataContext> instance, the object is considered to be in the `PossiblyModified` state.</span></span> <span data-ttu-id="0fdf0-185">Sie können auf drei Weisen erzwingen, dass ein angefügtes Objekt als Objekt im `Modified`-Zustand betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-185">There are three ways to force an attached object to be considered `Modified`.</span></span>  
  
1. <span data-ttu-id="0fdf0-186">Fügen Sie es als unverändert an, und ändern Sie die Felder dann direkt.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-186">Attach it as unmodified, and then directly modify the fields.</span></span>  
  
2. <span data-ttu-id="0fdf0-187">Fügen Sie es mit der <xref:System.Data.Linq.Table%601.Attach%2A>-Überladung an, die aktuelle und ursprüngliche Objektinstanzen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-187">Attach it with the <xref:System.Data.Linq.Table%601.Attach%2A> overload that takes current and original object instances.</span></span> <span data-ttu-id="0fdf0-188">Dadurch werden dem Änderungsprotokollierer alte und neue Werte zur Verfügung gestellt, sodass er automatisch weiß, welche Felder geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-188">This supplies the change tracker with old and new values so that it will automatically know which fields have changed.</span></span>  
  
3. <span data-ttu-id="0fdf0-189">Fügen Sie es mit der <xref:System.Data.Linq.Table%601.Attach%2A>-Überladung an, die einen zweiten booleschen Parameter (auf true festgelegt) akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-189">Attach it with the <xref:System.Data.Linq.Table%601.Attach%2A> overload that takes a second Boolean parameter (set to true).</span></span> <span data-ttu-id="0fdf0-190">Dadurch wird das Objekt vom Änderungsprotokollierer als geändert betrachtet, ohne dass einer der ursprünglichen Werte bereitgestellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-190">This will tell the change tracker to consider the object modified without having to supply any original values.</span></span> <span data-ttu-id="0fdf0-191">Bei dieser Vorgehensweise muss dass Objekt über ein Versions-/Timestampfeld verfügen.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-191">In this approach, the object must have a version/timestamp field.</span></span>  
  
 <span data-ttu-id="0fdf0-192">Weitere Informationen finden Sie unter [Objekt Zustände und Änderungs Nachverfolgung](object-states-and-change-tracking.md).</span><span class="sxs-lookup"><span data-stu-id="0fdf0-192">For more information, see [Object States and Change-Tracking](object-states-and-change-tracking.md).</span></span>  
  
 <span data-ttu-id="0fdf0-193">Wenn ein Entitätsobjekt mit derselben Identität wie das angefügte Objekt bereits im ID-Cache enthalten ist, wird eine <xref:System.Data.Linq.DuplicateKeyException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-193">If an entity object already occurs in the ID Cache with the same identity as the object being attached, a <xref:System.Data.Linq.DuplicateKeyException> is thrown.</span></span>  
  
 <span data-ttu-id="0fdf0-194">Wenn Sie es mit einem `IEnumerable`-Satz von Objekten anfügen, wird eine <xref:System.Data.Linq.DuplicateKeyException> ausgelöst, wenn ein bereits vorhandener Schlüssel vorliegt.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-194">When you attach with an `IEnumerable` set of objects, a <xref:System.Data.Linq.DuplicateKeyException> is thrown when an already existing key is present.</span></span> <span data-ttu-id="0fdf0-195">Verbleibende Objekte werden nicht angefügt.</span><span class="sxs-lookup"><span data-stu-id="0fdf0-195">Remaining objects are not attached.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fdf0-196">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0fdf0-196">See also</span></span>

- [<span data-ttu-id="0fdf0-197">N-Tier-und Remote Anwendungen mit LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0fdf0-197">N-Tier and Remote Applications with LINQ to SQL</span></span>](n-tier-and-remote-applications-with-linq-to-sql.md)
- [<span data-ttu-id="0fdf0-198">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="0fdf0-198">Background Information</span></span>](background-information.md)
