---
title: "Implementieren von Gesch&#228;ftslogik (LINQ to SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c4577590-7b12-42e1-84a6-95aa2562727e
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Implementieren von Gesch&#228;ftslogik (LINQ to SQL)
Der Begriff "Geschäftslogik" bezieht sich in diesem Thema auf benutzerdefinierte Regeln oder Validierungstests, die auf Daten angewendet werden, bevor diese eingefügt, aktualisiert oder aus der Datenbank gelöscht werden.  Der Begriff Geschäftslogik wird zeitweise synonym mit "Geschäftsregeln" oder "Domänenlogik" verwendet. In N\-Tier\-Anwendungen wird Geschäftslogik normalerweise als logische Ebene bezeichnet, die somit unabhängig von der Präsentationsebene oder Datenzugriffsebene geändert werden kann.  Die Geschäftslogik kann von der Datenzugriffsebene aufgerufen werden, bevor oder nachdem Daten in der Datenbank aktualisiert, eingefügt oder gelöscht werden.  
  
 Mit der Geschäftslogik kann genauso einfach wie anhand einer Schemavalidierung festgestellt werden, ob der Typ des Feldes mit dem Typ der Tabellenspalte kompatibel ist.  Alternativ kann sie aus einem Satz von Objekten bestehen, die auf beliebig komplexe Weisen interagieren.  Die Regeln werden möglicherweise als gespeicherte Prozeduren in der Datenbank oder als Objekte im Arbeitsspeicher implementiert.  Wenn jedoch die Geschäftslogik implementiert ist, ermöglicht Ihnen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die Verwendung von partiellen Klassen und Methoden, um die Geschäftslogik vom Datenzugriffscode zu trennen.  
  
## Aufrufen der Geschäftslogik durch LINQ to SQL  
 Wenn Sie eine Entitätsklasse zur Entwurfszeit entweder manuell oder mithilfe von [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] oder SQLMetal generieren, wird sie als partielle Klasse festgelegt.  Dies bedeutet, dass Sie in einer separaten Codedatei einen anderen Teil der Entitätsklasse festlegen können, in der die benutzerdefinierte Geschäftslogik enthalten ist.  Zur Kompilierungszeit werden die beiden Teile in eine einzelne Klasse zusammengeführt. Wenn Sie Entitätskassen mithilfe von [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] oder SQLMetal regenerieren müssen, können Sie dies tun, ohne dass Ihr Teil der Klasse geändert wird.  
  
 Die partiellen Klassen, durch die Entitäten definiert werden, und <xref:System.Data.Linq.DataContext> enthalten partielle Methoden.  Dabei handelt es sich um Erweiterungspunkte, über die Sie die Geschäftslogik anwenden können, bevor und nachdem Sie Updates, Einfügungen oder Löschungen für eine Entität oder Entitätseigenschaft ausführen.  Partielle Methoden können als Kompilierungsereignisse betrachtet werden.  Der Code\-Generator definiert eine Methodensignatur und ruft die Methoden in den get\- und set\-Eigenschaftenaccessoren, im `DataContext`\-Konstruktor und in einigen Fällen im Hintergrund auf, sobald <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen wird.  Wenn Sie jedoch keine bestimmte partielle Methode implementieren, werden alle darauf gerichteten Verweise sowie die Definition während der Kompilierung entfernt.  
  
 In der Implementierungsdefinition, die Sie in eine separate Codedatei schreiben, können Sie beliebige benutzerdefinierte Logik aufnehmen.  Sie können die partielle Klasse selbst als Domänenebene verwenden oder einen Aufruf von der Implementierungsdefinition der partiellen Methode in separate Objekte ausführen.  Die Geschäftslogik wird auf beide Weisen klar sowohl vom Datenzugriffscode als auch vom Präsentationsebenencode getrennt.  
  
## Genauere Betrachtung der Erweiterungspunkte  
 Im folgenden Beispiel wird der Teil des Codes veranschaulicht, der von [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] für die `DataContext`\-Klasse generiert wird. Diese verfügt über zwei Tabellen: `Customers` und `Orders`.  Beachten Sie, dass Einfüge\-, Update\- und Löschmethoden für jede Tabelle in der Klasse definiert werden.  
  
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
  
 Wenn Sie die Einfüge\-, Update\- und Löschmethoden in Ihrer partiellen Klasse implementieren, werden sie von der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Laufzeit anstelle ihrer eigenen Standardmethoden aufgerufen, sobald <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen wird.  Auf diese Weise können Sie das Standardverhalten für Erstellungs\-, Lese\-, Update\- und Löschoperationen überschreiben.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anpassen des Einfüge\-, Update\- und Löschverhaltens von Entitätsklassen](../Topic/Walkthrough:%20Customizing%20the%20insert,%20update,%20and%20delete%20behavior%20of%20entity%20classes.md).  
  
 Die `OnCreated`\-Methode wird im Klassenkonstruktor aufgerufen.  
  
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
  
 Die Entitätsklassen verfügen über drei Methoden, die von der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Laufzeit aufgerufen werden, wenn die Entität \(beim Aufrufen von `SubmitChanges`\) erstellt, geladen und überprüft wird.  Die Entitätsklassen verfügen außerdem über zwei partielle Methoden für jede Eigenschaft, eine davon wird vor dem Festlegen der Eigenschaft und die andere danach aufgerufen.  Im folgenden Codebeispiel werden einige der für die `Customer`\-Klasse generierten Methoden veranschaulicht:  
  
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
  
 Die Methoden werden im set\-Accessor der Eigenschaft aufgerufen, wie im folgenden Beispiel für die `CustomerID`\-Eigenschaft veranschaulicht:  
  
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
  
 In Ihren Teil der Klasse schreiben Sie eine Implementierungsdefinition der Methode.  Nachdem Sie in [!INCLUDE[vsprvs](../../../../../../includes/vsprvs-md.md)] `partial` eingegeben haben, wird IntelliSense für die Methodendefinitionen im anderen Teil der Klasse angezeigt.  
  
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
  
 Weitere Informationen darüber, wie Sie Ihrer Anwendung mithilfe von partiellen Methoden Geschäftslogik hinzufügen, finden Sie in den folgenden Themen:  
  
 [Vorgehensweise: Hinzufügen von Validierungen zu Entitätsklassen](../Topic/How%20to:%20Add%20validation%20to%20entity%20classes.md)  
  
 [Exemplarische Vorgehensweise: Anpassen des Einfüge\-, Update\- und Löschverhaltens von Entitätsklassen](../Topic/Walkthrough:%20Customizing%20the%20insert,%20update,%20and%20delete%20behavior%20of%20entity%20classes.md)  
  
 [Exemplarische Vorgehensweise: Hinzufügen von Validierung zu Entitätsklassen](../Topic/Walkthrough:%20Adding%20Validation%20to%20Entity%20Classes.md)  
  
## Siehe auch  
 [Partielle Klassen und Methoden](../Topic/Partial%20Classes%20and%20Methods%20\(C%23%20Programming%20Guide\).md)   
 [Partial Methods](../Topic/Partial%20Methods%20\(Visual%20Basic\).md)   
 [LINQ to SQL\-Tools in Visual Studio](../Topic/LINQ%20to%20SQL%20Tools%20in%20Visual%20Studio2.md)   
 [SqlMetal.exe \(Tool zur Codegenerierung\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)