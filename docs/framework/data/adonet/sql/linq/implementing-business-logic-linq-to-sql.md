---
title: Implementieren von Geschäftslogik (LINQ to SQL)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c4577590-7b12-42e1-84a6-95aa2562727e
ms.openlocfilehash: d739e4bba96873740c53c07eccf687b060d82003
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43798870"
---
# <a name="implementing-business-logic-linq-to-sql"></a><span data-ttu-id="751e8-102">Implementieren von Geschäftslogik (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="751e8-102">Implementing Business Logic (LINQ to SQL)</span></span>
<span data-ttu-id="751e8-103">Der Begriff „Geschäftslogik“ bezieht sich in diesem Thema auf benutzerdefinierte Regeln oder Validierungstests, die auf Daten angewendet werden, bevor diese eingefügt, aktualisiert oder aus der Datenbank gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="751e8-103">The term "business logic" in this topic refers to any custom rules or validation tests that you apply to data before it is inserted, updated or deleted from the database.</span></span> <span data-ttu-id="751e8-104">Der Begriff Geschäftslogik wird zeitweise synonym mit "Geschäftsregeln" oder "Domänenlogik" verwendet.</span><span class="sxs-lookup"><span data-stu-id="751e8-104">Business logic is also sometimes referred to as "business rules" or "domain logic."</span></span> <span data-ttu-id="751e8-105">In N-Tier-Anwendungen wird Geschäftslogik normalerweise als logische Ebene bezeichnet, die somit unabhängig von der Präsentationsebene oder Datenzugriffsebene geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="751e8-105">In n-tier applications it is typically designed as a logical layer so that it can be modified independently of the presentation layer or data access layer.</span></span> <span data-ttu-id="751e8-106">Die Geschäftslogik kann von der Datenzugriffsebene aufgerufen werden, bevor oder nachdem Daten in der Datenbank aktualisiert, eingefügt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="751e8-106">The business logic can be invoked by the data access layer before or after any update, insertion, or deletion of data in the database.</span></span>  
  
 <span data-ttu-id="751e8-107">Mit der Geschäftslogik kann genauso einfach wie anhand einer Schemavalidierung festgestellt werden, ob der Typ des Feldes mit dem Typ der Tabellenspalte kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="751e8-107">The business logic can be as simple as a schema validation to make sure that the type of the field is compatible with the type of the table column.</span></span> <span data-ttu-id="751e8-108">Alternativ kann sie aus einem Satz von Objekten bestehen, die auf beliebig komplexe Weisen interagieren.</span><span class="sxs-lookup"><span data-stu-id="751e8-108">Or it can consist of a set of objects that interact in arbitrarily complex ways.</span></span> <span data-ttu-id="751e8-109">Die Regeln werden möglicherweise als gespeicherte Prozeduren in der Datenbank oder als Objekte im Arbeitsspeicher implementiert.</span><span class="sxs-lookup"><span data-stu-id="751e8-109">The rules may be implemented as stored procedures on the database or as in-memory objects.</span></span> <span data-ttu-id="751e8-110">Jedoch die Geschäftslogik implementiert wird, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] können Sie die partielle Klassen und Methoden verwenden, um die Geschäftslogik vom Datenzugriffscode zu trennen.</span><span class="sxs-lookup"><span data-stu-id="751e8-110">However the business logic is implemented, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] enables you use partial classes and partial methods to separate the business logic from the data access code.</span></span>  
  
## <a name="how-linq-to-sql-invokes-your-business-logic"></a><span data-ttu-id="751e8-111">Aufrufen der Geschäftslogik durch LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="751e8-111">How LINQ to SQL Invokes Your Business Logic</span></span>  
 <span data-ttu-id="751e8-112">Wenn Sie eine Entitätsklasse zur Entwurfszeit entweder manuell oder mithilfe von [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] oder SQLMetal generieren, wird sie als partielle Klasse festgelegt.</span><span class="sxs-lookup"><span data-stu-id="751e8-112">When you generate an entity class at design time, either manually or by using the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] or SQLMetal, it is defined as a partial class.</span></span> <span data-ttu-id="751e8-113">Dies bedeutet, dass Sie in einer separaten Codedatei einen anderen Teil der Entitätsklasse festlegen können, in der die benutzerdefinierte Geschäftslogik enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="751e8-113">This means that, in a separate code file, you can define another part of the entity class that contains your custom business logic.</span></span> <span data-ttu-id="751e8-114">Zur Kompilierungszeit werden die beiden Teile in eine einzelne Klasse zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="751e8-114">At compile time, the two parts are merged into a single class.</span></span> <span data-ttu-id="751e8-115">Wenn Sie Entitätskassen mithilfe von [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] oder SQLMetal regenerieren müssen, können Sie dies tun, ohne dass Ihr Teil der Klasse geändert wird.</span><span class="sxs-lookup"><span data-stu-id="751e8-115">But if you have to regenerate your entity classes by using the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] or SQLMetal, you can do so and your part of the class will not be modified.</span></span>  
  
 <span data-ttu-id="751e8-116">Die partiellen Klassen, durch die Entitäten definiert werden, und <xref:System.Data.Linq.DataContext> enthalten partielle Methoden.</span><span class="sxs-lookup"><span data-stu-id="751e8-116">The partial classes that define entities and the <xref:System.Data.Linq.DataContext> contain partial methods.</span></span> <span data-ttu-id="751e8-117">Dabei handelt es sich um Erweiterungspunkte, über die Sie die Geschäftslogik anwenden können, bevor und nachdem Sie Updates, Einfügungen oder Löschungen für eine Entität oder Entitätseigenschaft ausführen.</span><span class="sxs-lookup"><span data-stu-id="751e8-117">These are the extensibility points that you can use to apply your business logic before and after any update, insert, or delete for an entity or entity property.</span></span> <span data-ttu-id="751e8-118">Partielle Methoden können als Kompilierungsereignisse betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="751e8-118">Partial methods can be thought of as compile-time events.</span></span> <span data-ttu-id="751e8-119">Der Code-Generator definiert eine Methodensignatur und ruft die Methoden in den get- und set-Eigenschaftenaccessoren, im `DataContext`-Konstruktor und in einigen Fällen im Hintergrund auf, sobald <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="751e8-119">The code-generator defines a method signature and calls the methods in the get and set property accessors, the `DataContext` constructor, and in some cases behind the scenes when <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called.</span></span> <span data-ttu-id="751e8-120">Wenn Sie jedoch keine bestimmte partielle Methode implementieren, werden alle darauf gerichteten Verweise sowie die Definition während der Kompilierung entfernt.</span><span class="sxs-lookup"><span data-stu-id="751e8-120">However, if you do not implement a particular partial method, then all the references to it and the definition are removed at compile time.</span></span>  
  
 <span data-ttu-id="751e8-121">In der Implementierungsdefinition, die Sie in eine separate Codedatei schreiben, können Sie beliebige benutzerdefinierte Logik aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="751e8-121">In the implementing definition that you write in your separate code file, you can perform whatever custom logic is required.</span></span> <span data-ttu-id="751e8-122">Sie können die partielle Klasse selbst als Domänenebene verwenden oder einen Aufruf von der Implementierungsdefinition der partiellen Methode in separate Objekte ausführen.</span><span class="sxs-lookup"><span data-stu-id="751e8-122">You can use your partial class itself as your domain layer, or you can call from your implementing definition of the partial method into a separate object or objects.</span></span> <span data-ttu-id="751e8-123">Die Geschäftslogik wird auf beide Weisen klar sowohl vom Datenzugriffscode als auch vom Präsentationsebenencode getrennt.</span><span class="sxs-lookup"><span data-stu-id="751e8-123">Either way, your business logic is cleanly separated from both your data access code and your presentation layer code.</span></span>  
  
## <a name="a-closer-look-at-the-extensibility-points"></a><span data-ttu-id="751e8-124">Genauere Betrachtung der Erweiterungspunkte</span><span class="sxs-lookup"><span data-stu-id="751e8-124">A Closer Look at the Extensibility Points</span></span>  
 <span data-ttu-id="751e8-125">Das folgende Beispiel zeigt einen Teil vom generierten Code der [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] für die `DataContext` -Klasse, die verfügt über zwei Tabellen: `Customers` und `Orders`.</span><span class="sxs-lookup"><span data-stu-id="751e8-125">The following example shows part of the code generated by the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for the `DataContext` class that has two tables: `Customers` and `Orders`.</span></span> <span data-ttu-id="751e8-126">Beachten Sie, dass Einfüge-, Update- und Löschmethoden für jede Tabelle in der Klasse definiert werden.</span><span class="sxs-lookup"><span data-stu-id="751e8-126">Note that Insert, Update, and Delete methods are defined for each table in the class.</span></span>  
  
```vb  
Partial Public Class Northwnd  
    Inherits System.Data.Linq.DataContext  
  
    Private Shared mappingSource As _  
        System.Data.Linq.Mapping.MappingSource = New _  
        AttributeMappingSource  
  
    #Region "Extensibility Method Definitions"  
    Partial Private Sub OnCreated()  
    End Sub  
    Partial Private Sub InsertCustomer(instance As Customer)  
    End Sub  
    Partial Private Sub UpdateCustomer(instance As Customer)  
    End Sub  
    Partial Private Sub DeleteCustomer(instance As Customer)  
    End Sub  
    Partial Private Sub InsertOrder(instance As [Order])  
    End Sub  
    Partial Private Sub UpdateOrder(instance As [Order])  
    End Sub  
    Partial Private Sub DeleteOrder(instance As [Order])  
    End Sub  
    #End Region  
```  
  
```csharp  
public partial class MyNorthWindDataContext : System.Data.Linq.DataContext  
    {  
        private static System.Data.Linq.Mapping.MappingSource mappingSource = new AttributeMappingSource();  
  
        #region Extensibility Method Definitions  
        partial void OnCreated();  
        partial void InsertCustomer(Customer instance);  
        partial void UpdateCustomer(Customer instance);  
        partial void DeleteCustomer(Customer instance);  
        partial void InsertOrder(Order instance);  
        partial void UpdateOrder(Order instance);  
        partial void DeleteOrder(Order instance);  
        #endregion  
```  
  
 <span data-ttu-id="751e8-127">Wenn Sie die Einfüge-, Update- und Löschmethoden in Ihrer partiellen Klasse implementieren, werden sie von der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Laufzeit anstelle ihrer eigenen Standardmethoden aufgerufen, sobald <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="751e8-127">If you implement the Insert, Update and Delete methods in your partial class, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime will call them instead of its own default methods when <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called.</span></span> <span data-ttu-id="751e8-128">Auf diese Weise können Sie das Standardverhalten für Erstellungs-, Lese-, Update- und Löschoperationen überschreiben.</span><span class="sxs-lookup"><span data-stu-id="751e8-128">This enables you to override the default behavior for create / read / update / delete operations.</span></span> <span data-ttu-id="751e8-129">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anpassen des Einfüge-, Update- und delete-Verhalten von Entitätsklassen](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes).</span><span class="sxs-lookup"><span data-stu-id="751e8-129">For more information, see [Walkthrough: Customizing the insert, update, and delete behavior of entity classes](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes).</span></span>  
  
 <span data-ttu-id="751e8-130">Die `OnCreated`-Methode wird im Klassenkonstruktor aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="751e8-130">The `OnCreated` method is called in the class constructor.</span></span>  
  
```vb  
Public Sub New(ByVal connection As String)  
    MyBase.New(connection, mappingSource)  
    OnCreated()  
End Sub  
```  
  
```csharp  
public MyNorthWindDataContext(string connection) :  
            base(connection, mappingSource)  
        {  
            OnCreated();  
        }  
```  
  
 <span data-ttu-id="751e8-131">Die Entitätsklassen verfügen über drei Methoden, die von der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Laufzeit aufgerufen werden, wenn die Entität (beim Aufrufen von `SubmitChanges`) erstellt, geladen und überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="751e8-131">The entity classes have three methods that are called by the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime when the entity is created, loaded, and validated (when `SubmitChanges` is called).</span></span> <span data-ttu-id="751e8-132">Die Entitätsklassen verfügen außerdem über zwei partielle Methoden für jede Eigenschaft, eine davon wird vor dem Festlegen der Eigenschaft und die andere danach aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="751e8-132">The entity classes also have two partial methods for each property, one that is called before the property is set, and one that is called after.</span></span> <span data-ttu-id="751e8-133">Im folgenden Codebeispiel werden einige der für die `Customer`-Klasse generierten Methoden veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="751e8-133">The following code example shows some of the methods generated for the `Customer` class:</span></span>  
  
```vb  
#Region "Extensibility Method Definitions"  
    Partial Private Sub OnLoaded()  
    End Sub  
    Partial Private Sub OnValidate(action As _  
        System.Data.Linq.ChangeAction)  
    End Sub  
    Partial Private Sub OnCreated()  
    End Sub  
    Partial Private Sub OnCustomerIDChanging(value As String)  
    End Sub  
    Partial Private Sub OnCustomerIDChanged()  
    End Sub  
    Partial Private Sub OnCompanyNameChanging(value As String)  
    End Sub  
    Partial Private Sub OnCompanyNameChanged()  
    End Sub  
' ...Additional Changing/Changed methods for each property.  
```  
  
```csharp  
#region Extensibility Method Definitions  
    partial void OnLoaded();  
    partial void OnValidate();  
    partial void OnCreated();  
    partial void OnCustomerIDChanging(string value);  
    partial void OnCustomerIDChanged();  
    partial void OnCompanyNameChanging(string value);  
    partial void OnCompanyNameChanged();  
// ...additional Changing/Changed methods for each property  
```  
  
 <span data-ttu-id="751e8-134">Die Methoden werden im set-Accessor der Eigenschaft aufgerufen, wie im folgenden Beispiel für die `CustomerID`-Eigenschaft veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="751e8-134">The methods are called in the property set accessor as shown in the following example for the `CustomerID` property:</span></span>  
  
```vb  
Public Property CustomerID() As String  
    Set  
        If (String.Equals(Me._CustomerID, value) = False) Then  
            Me.OnCustomerIDChanging(value)  
            Me.SendPropertyChanging()  
            Me._CustomerID = value  
            Me.SendPropertyChanged("CustomerID")  
            Me.OnCustomerIDChanged()  
        End If  
    End Set  
End Property  
```  
  
```csharp  
public string CustomerID  
{  
    set  
    {  
        if ((this._CustomerID != value))  
        {  
            this.OnCustomerIDChanging(value);  
            this.SendPropertyChanging();  
            this._CustomerID = value;  
            this.SendPropertyChanged("CustomerID");  
            this.OnCustomerIDChanged();  
        }  
     }  
}  
```  
  
 <span data-ttu-id="751e8-135">In Ihren Teil der Klasse schreiben Sie eine Implementierungsdefinition der Methode.</span><span class="sxs-lookup"><span data-stu-id="751e8-135">In your part of the class, you write an implementing definition of the method.</span></span> <span data-ttu-id="751e8-136">In Visual Studio nach der Eingabe `partial` IntelliSense wird für die Methodendefinitionen im anderen Teil der Klasse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="751e8-136">In Visual Studio, after you type `partial` you will see IntelliSense for the method definitions in the other part of the class.</span></span>  
  
```vb  
Partial Public Class Customer  
    Private Sub OnCustomerIDChanging(value As String)  
        ' Perform custom validation logic here.  
    End Sub  
End Class  
```  
  
```csharp  
partial class Customer   
    {  
        partial void OnCustomerIDChanging(string value)  
        {  
            //Perform custom validation logic here.  
        }  
    }  
```  
  
 <span data-ttu-id="751e8-137">Weitere Informationen darüber, wie Sie Ihrer Anwendung mithilfe von partiellen Methoden Geschäftslogik hinzufügen, finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="751e8-137">For more information about how to add business logic to your application by using partial methods, see the following topics:</span></span>  
  
 [<span data-ttu-id="751e8-138">Gewusst wie: Hinzufügen von Validierungen zu Entitätsklassen</span><span class="sxs-lookup"><span data-stu-id="751e8-138">How to: Add validation to entity classes</span></span>](/visualstudio/data-tools/how-to-add-validation-to-entity-classes)  
  
 [<span data-ttu-id="751e8-139">Exemplarische Vorgehensweise: Anpassen des Einfüge-, Update- und Löschverhaltens in Entitätsklassen</span><span class="sxs-lookup"><span data-stu-id="751e8-139">Walkthrough: Customizing the insert, update, and delete behavior of entity classes</span></span>](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes)  
  
 [<span data-ttu-id="751e8-140">Exemplarische Vorgehensweise: Hinzufügen einer Validierung zu Entitätsklassen</span><span class="sxs-lookup"><span data-stu-id="751e8-140">Walkthrough: Adding Validation to Entity Classes</span></span>](https://msdn.microsoft.com/library/85b06a02-b2e3-4534-95b8-d077c8d4c1d7)  
  
## <a name="see-also"></a><span data-ttu-id="751e8-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="751e8-141">See Also</span></span>  
 [<span data-ttu-id="751e8-142">Partielle Klassen und Methoden</span><span class="sxs-lookup"><span data-stu-id="751e8-142">Partial Classes and Methods</span></span>](~/docs/csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)  
 [<span data-ttu-id="751e8-143">Partielle Methoden</span><span class="sxs-lookup"><span data-stu-id="751e8-143">Partial Methods</span></span>](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md)  
 [<span data-ttu-id="751e8-144">LINQ to SQL-Tools in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="751e8-144">LINQ to SQL Tools in Visual Studio</span></span>](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)  
 [<span data-ttu-id="751e8-145">SqlMetal.exe (Tool zur Codegenerierung)</span><span class="sxs-lookup"><span data-stu-id="751e8-145">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
