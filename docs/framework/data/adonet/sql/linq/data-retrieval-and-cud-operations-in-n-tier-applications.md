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
# <a name="data-retrieval-and-cud-operations-in-n-tier-applications-linq-to-sql"></a>Datenabruf und CUD-Operationen in n-schichtigen Anwendungen (LINQ to SQL)

Wenn Sie Entitätsobjekte wie Customers oder Orders über ein Netzwerk an einen Client serialisieren, werden diese Entitäten von ihrem Datenkontext getrennt. Änderungen oder Verknüpfungen mit anderen Objekten werden vom Datenkontext nicht mehr verfolgt. Dies stellt kein Problem dar, solange die Clients die Daten nur lesen. Es ist außerdem relativ einfach, Clients zu ermöglichen, einer Datenbank neue Zeilen hinzuzufügen. Wenn Ihre Anwendung jedoch voraussetzt, dass Clients Daten aktualisieren oder löschen sollen, müssen Sie die Entitäten an einen neuen Datenkontext anfügen, bevor Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType> aufrufen. Wenn Sie eine Überprüfung auf vollständige Parallelität mit ursprünglichen Werten verwenden, müssen Sie außerdem eine Möglichkeit schaffen, der Datenbank sowohl die ursprüngliche als auch die geänderte Entität bereitzustellen. Die `Attach`-Methoden werden bereitgestellt, um es Ihnen zu ermöglichen, Entitäten in einen neuen Datenkontext einzufügen, nachdem sie getrennt wurden.  
  
 Auch wenn Sie Proxy Objekte anstelle der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Entitäten serialisieren, müssen Sie immer noch eine Entität auf der Datenzugriffs Schicht (Data Access Layer, DAL) erstellen und Sie an einen neuen anfügen <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> , um die Daten an die Datenbank zu übermitteln.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ist vollständig für die Serialisierung von Entitäten nicht gleich. Weitere Informationen zur Verwendung der objektrelationaler Designer-und SQLMetal-Tools zum Generieren von Klassen, die mit Windows Communication Foundation (WCF) serialisierbar sind, finden Sie unter Gewusst [wie: Erstellen von serialisierbaren Entitäten](how-to-make-entities-serializable.md).  
  
> [!NOTE]
> Rufen Sie die `Attach`-Methoden nur für neue oder deserialisierte Entitäten auf. Die einzige Möglichkeit, eine Entität von ihrem ursprünglichen Datenkontext zu trennen, besteht darin, sie zu serialisieren. Wenn Sie versuchen, eine nicht getrennte Entität an einen neuen Datenkontext anzufügen, und diese Entität noch über verzögerte Ladeprogramme aus dem vorherigen Datenkontext verfügt, löst [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] eine Ausnahme aus. Eine Entität mit verzögerten Ladenprogrammen aus zwei unterschiedlichen Datenkontexten könnte unerwünschte Ergebnisse hervorbringen, wenn Sie Einfüge-, Aktualisierungs- und Löschvorgänge für diese Entität ausführen. Weitere Informationen zu verzögerten Lade Programmen finden Sie unter [Verzögertes oder sofortiges Laden](deferred-versus-immediate-loading.md).  
  
## <a name="retrieving-data"></a>Abrufen von Daten  
  
### <a name="client-method-call"></a>Clientmethodenaufruf  

 In den folgenden Beispielen wird ein Beispielmethodenaufruf der DAL von einem Windows Forms-Client aus veranschaulicht. Die DAL wird in diesem Beispiel als Windows-Dienstbibliothek implementiert:  
  
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
  
### <a name="middle-tier-implementation"></a>Implementierung auf der mittleren Ebene  

 Im folgenden Beispiel wird eine Implementierung der Schnittstellenmethode auf der mittleren Ebene veranschaulicht. Die folgenden beiden Hauptpunkte sind zu beachten:  
  
- <xref:System.Data.Linq.DataContext> wird im Methodenbereich deklariert.  
  
- Die Methode gibt eine <xref:System.Collections.IEnumerable>-Auflistung der tatsächlichen Ergebnisse zurück. Das Serialisierungsprogramm führt die Abfrage aus, um die Ergebnisse an die Client- oder Präsentationsebene zurückzusenden. Um lokal auf der mittleren Ebene auf die Abfrageergebnisse zuzugreifen, können Sie die Ausführung erzwingen, indem Sie `ToList` oder `ToArray` für die Abfragevariable aufrufen. Anschließend können Sie diese Liste oder dieses Array als `IEnumerable` zurückgeben.  
  
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
  
 Eine Instanz eines Datenkontexts sollte eine Lebensdauer von einer "Arbeitseinheit" haben. In einer lose verknüpften Umgebung ist eine Arbeitseinheit normalerweise klein und entspricht vielleicht einer vollständigen Transaktion, einschließlich eines einzelnen Aufrufs von `SubmitChanges`. Der Datenkontext wird deshalb im Methodenbereich erstellt und freigegeben. Wenn die Arbeitseinheit Aufrufe einer Geschäftsregellogik einschließt, behalten Sie die `DataContext`-Instanz im Allgemeinen für die gesamte Operation bei. `DataContext`-Instanzen sind grundsätzlich nicht dafür vorgesehen, über einen längeren Zeitraum für eine beliebige Anzahl von Transaktionen beibehalten zu werden.  
  
 Diese Methode gibt Product-Objekte, aber keine Auflistung von Order_Detail-Objekten zurück, die mit den einzelnen Produkten verknüpft sind. Verwenden Sie das <xref:System.Data.Linq.DataLoadOptions>-Objekt, um dieses Standardverhalten zu ändern. Weitere Informationen finden Sie unter Gewusst [wie: Steuern, wie viele verwandte Daten abgerufen](how-to-control-how-much-related-data-is-retrieved.md)werden.  
  
## <a name="inserting-data"></a>Einfügen von Daten  

 Um ein neues Objekt einzufügen, ruft die Präsentationsebene nur die relevante Methode für die Schnittstelle der mittleren Ebene auf und übergibt das neue einzufügende Objekt. In einigen Fällen kann es effizienter sein, wenn der Client nur einige Werte übergibt und das Erstellen des vollständigen Objekts der mittleren Ebene überlässt.  
  
### <a name="middle-tier-implementation"></a>Implementierung auf der mittleren Ebene  

 Auf der mittleren Ebene wird ein neuer <xref:System.Data.Linq.DataContext> erstellt, das Objekt mithilfe der <xref:System.Data.Linq.DataContext>-Methode an <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> angefügt und das Objekt beim Aufrufen von <xref:System.Data.Linq.DataContext.SubmitChanges%2A> eingefügt. Ausnahmen, Rückrufe und Fehlerbedingungen können wie in jedem beliebigen anderen Webdienstszenario behandelt werden.  
  
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
  
## <a name="deleting-data"></a>Löschen von Daten  

 Um ein vorhandenes Objekt aus der Datenbank zu löschen, ruft die Präsentationsebene die relevante Methode für die Schnittstelle der mittleren Ebene auf und übergibt eine Kopie, in der die ursprünglichen Werte des zu löschenden Objekts enthalten sind.  
  
 Löschvorgänge umfassen Überprüfungen auf vollständige Parallelität, und das zu löschende Objekt muss zuerst an den neuen Datenkontext angefügt werden. In diesem Beispiel wird der `Boolean`-Parameter auf `false` festgelegt, um anzuzeigen, dass das Objekt über keinen Timestamp (RowVersion) verfügt. Wenn die Datenbanktabelle Timestamps für jeden Datensatz generiert, sind Überprüfungen auf Parallelität besonders für den Client bedeutend einfacher auszuführen. Übergeben Sie entweder das ursprüngliche oder geänderte Objekt, und legen Sie den `Boolean`-Parameter auf `true` fest. Auf der mittleren Ebene ist es grundsätzlich erforderlich, die <xref:System.Data.Linq.ChangeConflictException> abzufangen. Weitere Informationen zum Behandeln von Konflikten bei der vollständigen Parallelität finden Sie unter [optimistische Parallelität: Übersicht](optimistic-concurrency-overview.md).  
  
 Beim Löschen von Entitäten, die über Fremdschlüsseleinschränkungen für verknüpfte Tabellen verfügen, müssen Sie zuerst alle Objekte in den zugehörigen <xref:System.Data.Linq.EntitySet%601>-Auflistungen löschen.  
  
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
  
## <a name="updating-data"></a>Aktualisieren von Daten  

 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt Updates in folgenden Szenarien mit vollständiger Parallelität:  
  
- Vollständige Parallelität auf der Grundlage von Timestamps oder RowVersion-Nummern  
  
- Vollständige Parallelität auf der Grundlage ursprünglicher Werte einer Teilmenge von Entitätseigenschaften  
  
- Vollständige Parallelität auf der Grundlage der vollständigen ursprünglichen und geänderten Entitäten  
  
 Sie können auch Update- oder Löschvorgänge für eine Entität und ihre Beziehungen ausführen, beispielsweise für einen Kunden und eine Auflistung der zugehörigen Bestellobjekte. Wenn Sie auf dem Client Änderungen an einem Diagramm von Entitätsobjekten und deren untergeordneten (`EntitySet`) Auflistungen vornehmen und für Überprüfungen auf vollständige Parallelität ursprüngliche Werte erforderlich sind, muss der Client diese ursprünglichen Werte für jede Entität und jedes <xref:System.Data.Linq.EntitySet%601>-Objekt bereitstellen. Wenn Clients in der Lage sein sollen, eine Reihe verknüpfter Updates, Löschungen und Einfügungen in einem einzelnen Methodenaufruf auszuführen, müssen Sie auf dem Client eine Möglichkeit vorsehen, um anzuzeigen, welcher Operationstyp für welche Entität ausgeführt werden soll. Auf der mittleren Ebene müssen Sie anschließend die geeignete <xref:System.Data.Linq.ITable.Attach%2A>-Methode und dann <xref:System.Data.Linq.ITable.InsertOnSubmit%2A>, <xref:System.Data.Linq.ITable.DeleteAllOnSubmit%2A> oder <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> (ohne `Attach`, für Einfügungen) für jede Entität aufrufen, bevor Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen. Das Abrufen von Daten aus der Datenbank ist keine zulässige Methode, um ursprüngliche Werte zu erhalten, bevor Sie ein Update versuchen.  
  
 Weitere Informationen zur vollständigen Parallelität finden Sie unter [optimistische Parallelität: Übersicht](optimistic-concurrency-overview.md). Ausführliche Informationen zum Auflösen von Konflikten bei der vollständigen Parallelität finden Sie unter Gewusst [wie: Verwalten von Änderungs Konflikten](how-to-manage-change-conflicts.md).  
  
 In den folgenden Beispielen werden die einzelnen Szenarien veranschaulicht:  
  
### <a name="optimistic-concurrency-with-timestamps"></a>Vollständige Parallelität mit Timestamps  
  
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
  
### <a name="with-subset-of-original-values"></a>Mit einer Teilmenge ursprünglicher Werte  

 Bei dieser Vorgehensweise gibt der Client das vollständige serialisierte Objekt zusammen mit den zu ändernden Werten zurück.  
  
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
  
### <a name="with-complete-entities"></a>Mit vollständigen Entitäten  
  
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
  
 Um eine Auflistung zu aktualisieren, rufen Sie <xref:System.Data.Linq.ITable.AttachAll%2A> anstelle von `Attach` auf.  
  
### <a name="expected-entity-members"></a>Erwartete Entitätsmember  

 Wie bereits erwähnt, müssen nur bestimmte Member des Entitätsobjekts festgelegt werden, bevor Sie die `Attach`-Methoden aufrufen. Entitätsmember, die festgelegt werden müssen, sollten folgenden Kriterien erfüllen:  
  
- Sie müssen Teil der Identität der Entität sein.  
  
- Von ihnen wird erwartet, dass sie sich ändern.  
  
- Es muss sich um einen Timestamp handeln oder ihr <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Attribut muss auf einen anderen Wert als `Never` festgelegt sein.  
  
 Wenn eine Tabelle einen Timestamp oder eine Versionsnummer für die Prüfung auf vollständige Parallelität verwendet, müssen diese Member daher festgelegt sein, bevor Sie <xref:System.Data.Linq.ITable.Attach%2A> aufrufen. Ein Member gilt als für die Überprüfung auf vollständige Parallelität festgelegt, wenn die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>-Eigenschaft für dieses Spaltenattribut auf true festgelegt ist. Alle angeforderten Updates werden nur gesendet, wenn der Wert für die Versionsnummer oder den Timestamp in Datenbank identisch ist.  
  
 Member werden ebenfalls in der Überprüfung auf vollständige Parallelität verwendet, solange <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> für den Member nicht auf `Never` festgelegt wurde. Sofern nicht anders angegeben, lautet der Standardwert `Always`.  
  
 Wenn einer dieser erforderlichen Member fehlt, wird während <xref:System.Data.Linq.ChangeConflictException> ("Zeile nicht gefunden oder geändert") eine <xref:System.Data.Linq.DataContext.SubmitChanges%2A> ausgelöst.  
  
### <a name="state"></a>State  

 Nachdem ein Entitätsobjekt an die <xref:System.Data.Linq.DataContext>-Instanz angefügt wurde, wird davon ausgegangen, dass sich das Objekt im `PossiblyModified`-Zustand befindet. Sie können auf drei Weisen erzwingen, dass ein angefügtes Objekt als Objekt im `Modified`-Zustand betrachtet wird.  
  
1. Fügen Sie es als unverändert an, und ändern Sie die Felder dann direkt.  
  
2. Fügen Sie es mit der <xref:System.Data.Linq.Table%601.Attach%2A>-Überladung an, die aktuelle und ursprüngliche Objektinstanzen akzeptiert. Dadurch werden dem Änderungsprotokollierer alte und neue Werte zur Verfügung gestellt, sodass er automatisch weiß, welche Felder geändert wurden.  
  
3. Fügen Sie es mit der <xref:System.Data.Linq.Table%601.Attach%2A>-Überladung an, die einen zweiten booleschen Parameter (auf true festgelegt) akzeptiert. Dadurch wird das Objekt vom Änderungsprotokollierer als geändert betrachtet, ohne dass einer der ursprünglichen Werte bereitgestellt werden muss. Bei dieser Vorgehensweise muss dass Objekt über ein Versions-/Timestampfeld verfügen.  
  
 Weitere Informationen finden Sie unter [Objekt Zustände und Änderungs Nachverfolgung](object-states-and-change-tracking.md).  
  
 Wenn ein Entitätsobjekt mit derselben Identität wie das angefügte Objekt bereits im ID-Cache enthalten ist, wird eine <xref:System.Data.Linq.DuplicateKeyException> ausgelöst.  
  
 Wenn Sie es mit einem `IEnumerable`-Satz von Objekten anfügen, wird eine <xref:System.Data.Linq.DuplicateKeyException> ausgelöst, wenn ein bereits vorhandener Schlüssel vorliegt. Verbleibende Objekte werden nicht angefügt.  
  
## <a name="see-also"></a>Weitere Informationen

- [N-Tier-und Remote Anwendungen mit LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md)
- [Hintergrundinformationen](background-information.md)
